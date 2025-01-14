# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
## Dockerを使った開発環境の構築
以下を順番に実行する。
```
$ docker compose build
```
```
$ docker compose run --rm bundle exec rails db:create
```
```
$ docker compose run --rm bundle exec rails db:migrate
```
```
$ docker compose up
```
`localhost:3000`にアクセスしてトップが表示される。

# groovy-grouping

勉強会でグループ分けをしたい。
ある基準（事業部・技術レベル）で均等になるようにしたい。
参加者はある程度決まっているが、その場にならないとわからない。
ランダム性をもたせたい。

## メモ

- グループ
  - 一意の値を入れる（URL用）
  - ステータス
  - どう分ける？
    - 人数でわけるパターン
    - グループ数で分けるパターン
- ユーザー
  - チームに入れる（ユーザーはチームごとでいいので、has_manyで）
  - 参加・不参加・わからんフラグ？
  - ステータス

 最低限の機能を満たすならこれで行けそう。
 グループに入れる人なら、ある程度性善説の設計でいい。
 むしろ、他の人が誰かの代わりに変えてあげられる方がいい。

firebase使おうかと思ったけど、RDSの方が早そう……。herokuでもいいな
https://sekigime.herokuapp.com
これをオマージュすればよさそう。

## 要望

前回とできるだけ違うようになるように（logの持たせ方を考えないといけない）


## 動線想定

トップ→チームの作成→招待（パスコード必要？）→ユーザー追加→ぽちっとなで作成
作成ログを残しておいてもいいかもね（複数候補から選べる）


グループとチームは多対多でもいいかもしれん。
