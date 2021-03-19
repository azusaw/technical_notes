# PostgresSQL

### 使い方

##### Linux

* postgres ユーザーで実施(su - postgres)
* postgresのbinディレクトリ以下で実行
	
	```
	$　./pg_ctl -D ../data/ stop
	
	$　./pg_ctl -D ../data/ start
  ```

##### Windows
 
* postgresのbinディレクトリ以下で実行
	
	```
	> pg_ctl.exe -D ../data/ stop

	> pg_ctl.exe -D ../data/start
  ```
	
### pgAdminへのつなげかた
* サーバー側で5432ポートを空ける
  ```
	firewall-cmd --add-port=5432/tcp --zone=public --permanent 
	firewall-cmd --reload
  ```

* /hogehoge/postgresql/data/pg_hba.conf を編集(/var/lib/pgsql/9.3/data にあるかも)
  ```
	# IPv4 local connections:
	host    all             all             127.0.0.1/32            trust
	host    all             all             172.xx.xx.xx/32         trust
  ```
	
* /hogehoge/postgresql/data/postgresql.conf を編集
  ```
	#listen_addresses = 'localhost'         # what IP address(es) to listen on;
	listen_addresses = '*'　←これをいれる
  ```

* postgres再起動

### 操作
|操作|コマンド|
|---|---|
|psqlに入る|psql -h localhost hulftiot|
|テーブルの一覧|\d|
|プライマリーキーを指定してテーブル作成|create table tablename (word char(1024) NOT NULL PRIMARY KEY, count int);|
|テーブル削除|drop table tablename;|


