# Oracle

### 管理者でログイン
```
Sqlplus sys as sysdba
```

### 文字コードの確認方法
```
SELECT VALUE FROM NLS_DATABASE_PARAMETERS WHERE PARAMETER='NLS_CHARACTERSET';
```

### プラガブル・データベースにつなぐ
12cから追加されたマルチテナントアーキテクチャ。
```
$ sqlplus system/Pass0123@localhost:1521/pdborcl.hoge.fuga.co.jp
```

### 接続識別子が知りたい

SYSTEMユーザーで以下実行
```
select instance_name from v$instance;
```

### 全テーブルのレコード数を出力する方法
```
select table_name, num_rows from user_tables order by table_name;
```

### 実行計画を確認したい
SELECT文を記述してCtrl+E

