# socialpoll

## システムの実行

### NSQ

`nsqlookupd`
`nsqd --lookupd-tcp-address=localhost:4160`

### MongoDB

`mongod --dbpath ./db`

### counter

```
cd counter
go install
counter
```

### twittervotes

```
cd twittervotes
go install
twittervotes
```

### api

```
cd api
go install
api
```

### web

```
cd web
go install
web
```

`http://localhost:8081`

## API

`?key=abc123`

```
/polls/
/polls/{id}
```

### Create

`curl --data '{"title":"調査のテスト","options":["one","two","three"]}' -X POST http://localhost:8080/polls/?key=abc123`

### Read


`curl -X GET http://localhost:8080/polls/?key=abc123`
`curl -X GET http://localhost:8080/polls/5a4af686f58b79cb94162193?key=abc123`

### Delete

`curl -X DELETE http://localhost:8080/polls/5a4af686f58b79cb94162193?key=abc123`

## mongodの起動

```console
$ mongod --dbpath ./db
```

## mongoとのインタラクション

```console
$ mongo
> use ballots
> db.polls.insert({"title":"調査のテスト1","options":["one","two","three"]})
> db.polls.insert({"title":"調査のテスト2","options":["four","five","six"]})
```
