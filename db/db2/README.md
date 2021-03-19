# DB2

### 接続

db2 で対話開始
connect to [dbname]を行ってからSELECTなどを行う

### INSPECTコマンド

データ容量なとを検査するコマンド。出力先を指定するし、ファイルを吐き出す。

### 設定値を確認
```
db2 "GET DATABASE MANAGER CONFIGURATION"

inspect check table name [tablename] results keep /home/db2inst1/hoge

list tables show detail
```
