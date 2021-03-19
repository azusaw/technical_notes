# MySQL

### log
Windows
My.iniに以下追加。
負荷がかかるので調査時以外は外したほうが良い。
```
[mysqld]
# すべてのクエリのログを出す
log=myquery.log
```

### トランザクション分離レベル

#### 初期値
`REPEATABLE READ`

この設定ではファントムリードが発生しない。
つまり、トランザクションが終了するまで**他トランザクションが行った変更を検知しない**。
（この挙動が2018年某製品で大障害を引き起こし、私を苦しめた）

#### 変更
```
SET GLOBAL TRANSACTION ISOLATION LEVEL read committed;
SET SESSION TRANSACTION ISOLATION LEVEL read committed;
```

#### 確認
```
SELECT @@global.tx_isolation;
SELECT @@session.tx_isolation; 
SHOW variables like 'tx_isolation'
```

#### GrobalとSessionの違い

grobalの値はmy.iniに設定、もしくはrootユーザで
`SET GLOBAL TRANSACTION ISOLATION LEVEL read committed;`で設定

sessionの値は、ユーザで
`SET SESSION TRANSACTION ISOLATION LEVEL read committed;`で設定

この手続きでないと動く形に変更できないので注意。

## MySQL WorkbenchでSELECTした結果を文字列で表示する方法

[edit] -> [Preferences] -> [SQL Execution]<br />
以下のチェックボックスをオンにする<br />
`[Treat BINARY/VARBINARY as nonbinary character string]`

### 文字コードの確認

```
show global variables like '%char%';
show variables like '%char%';
```

### 大文字小文字は区別されるか？

設定次第。
```
show variables where variable_name='lower_case_table_names';
```

### 文字列連結の"||"
MySQLでは設定変えないと使えない。CONCATを使おう。





