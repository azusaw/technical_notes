# DB

## RDB
* DB2
* MySQL
* Oracle
* PostgresSQL
* SQLServer

## DocumentDB
* mongoDB

## GraphDB
* Neo4j

## Index

### つけるべきもの
* WHERE句で検索条件にするもの
*  カーディナリティー（カラムに対してとりうる値の種類）が高いもの
* 外部キーとして使用されているもの

### つけない方がいいもの
* データ登録件数が少ないテーブル
* 頻繁にINSERT/UPDATE/DELETEされるテーブル

### ポイント
* 複合条件なら複合インデックスを作成する、この時複合順序をSQLに合わせないとダメ
*  複合順序はこの順番
  ```
  * FROM
  * ON
  * JOIN
  * WHERE
  * GROUP BY
  * HAVING
  * SELECT
  * DISTINCT
  * ORDER BY
  * TOP(LIMIT)
  ```
* 1クエリで1インデックス使える
* プライマリキーが条件の場合、インデックスは自動的に貼られているため不要
* インデックスを増やすとinsertに時間がかかるようになる
* インデックスの情報を保存するため、ディスク容量も増える

### Data Redundancy
#### 1NF: 第1正規形
1レコードの中で特定の項目が繰り返し含まれたり、複数の値を連結した値が含まれるような構造を廃したもの

|RepID*|Rep FirstName|Rep LastName|ClientID*|Client|Time WithClient|
|--|--|--|--|--|--|
|TS-89|Gilroy|Gladstone|782|KilroyInc.|9 hrs|
|RK-56|Mary|Mayhem|221|Italiana|67 hrs|

### 2NF: 第2正規形
1NFからキーの要素が複数あるテーブルの項目で、キーのどちらかにしか従属しない項目を分離する
|Rep ID*|Client ID*|Time With Client|
|--|--|--|
|TS-89|978|14 hrs|
|TS-89|665|26 hrs|

|Rep ID*|First Name|Last Name|
|--|--|--|
|TS-89|Gilroy|Gladstone|

|Client ID*|Client Name|
|--|--|
|978|US Corp|
|665|Taggarts|

### 3NF: 第3正規形
主キー以外の値によって、他の項目の内容が決定されないようにテーブルを分離する
