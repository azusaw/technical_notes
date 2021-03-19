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
