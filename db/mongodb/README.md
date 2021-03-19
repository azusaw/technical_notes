# MongoDB

#### 概要
- NoSQL
- RDBMSのようにレコードをテーブルに書く概念とは異なり、KVS(Key Value Store)と呼ばれるキーバリュー型DB
- `document`と呼ばれる構造的なデータをJSONライクな形式で表現
- `document`の集合体は`collection`として管理する
- documentはJSONのように階層構造を持たせることが可能
- シェア5位（1～4位は Oracle > MySQL > SQLServer > PostgresSQL）



#### 特徴

##### できること

- Valueを検索の条件にする（KVSではこれが難しかったりする）
- 複雑な改造構造のフォール度検索、ソート、集計

##### できないこと

- SQL操作（操作はJavaScriptで行う）
- RDBMSのような高度な結合操作
- トランザクション処理（バージョンや条件によっては実現可能）

 ⇒ ソシャゲ、webサイトの操作データログの蓄積などに向いている


#### インストール for Mac

```
# brew install mongodbがエラーになる場合はこちらを実行
$ brew tap  mongodb/brew
Tapping mongodb/brew
 
# communityはCommunity Editionのこと
$ brew install mongodb-community
 
# サービスの起動
$ brew services start mongodb-community
Successfully started `mongodb-community` 
```



#### 基本操作

```
# MongoDB に入る
$ mongo

# admin データベースに接続する
> use admin
switched to db admin

# 管理ユーザを登録
> db.createUser({user:"admin", pwd:"admin", roles:[{role:"root", db:"admin"}]})

# ユーザの存在確認
> db.getUsers()
 
# 一度抜ける
> exit
 
# 認証を有効にして再起動
> mongod --auth --dbpath /usr/local/var/mongodb
 
# MongoDBに入る
> mongo -u admin -p admin -authenticationDatabase admin
 
# ここからadminDBに対しての操作となる
```



#### DBとcollectionの操作

```
# DBの作成
$ mongo wata
 
# DBの切り替え
> use wata
 
# DB一覧を表示
# wataはまだCollectionがないので表示されない
> show dbs
 
# Collectionを作成
> db.createCollection('COL');
 
# Collction一覧を表示
> show collections
 
# Collectionにドキュメントを追加
> db.COL.insert( { lastname:'watanabe', firstname:'azusa'} );
WriteResult({ "nInserted" : 1 })
 
# Collection全件取得
> db.COL.find();
 
# 特定のドキュメントを取得
> db.COL.find( { lastname:'watanabe' } );
 
# ドキュメントの更新（ageプロパティを追加）
> db.COL.update( { lastname:'watanabe'}, {$set:{ age:26 } } );
```



#### 参考URL

[http://kageura.hatenadiary.jp/entry/2018/01/08/MongoDB%E4%BA%8B%E5%A7%8B%E3%82%81%E3%80%82%E5%80%8B%E4%BA%BA%E7%9A%84%E3%81%BE%E3%81%A8%E3%82%81](http://kageura.hatenadiary.jp/entry/2018/01/08/MongoDB事始め。個人的まとめ)

https://qiita.com/Brutus/items/8a67a4db0fdc5a33d549

