# socialpoll

## API

`?key=abc123`

```
/polls/
/polls/{id}
```

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
