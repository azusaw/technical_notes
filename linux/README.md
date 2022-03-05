# Linux
## curl

## dig

## dns
ドメイン名に対してIPアドレスを返す
```
$ nslookup www.yahoo.co.jp

Server:         89.101.160.4
Address:        89.101.160.4#53

Non-authoritative answer:
www.yahoo.co.jp canonical name = edge12.g.yimg.jp.
Name:   edge12.g.yimg.jp
Address: 183.79.217.124
```

## jq
JSON整形コマンド
```
$ echo '{"items":[{"item_id":1,"name":"すてきな雑貨","price":2500},{"item_id":2,"name":"格好いい置物","price":4500}]}' | jq '.items[].name'

"すてきな雑貨"
"格好いい置物"
```

## nkf
「nkf」は「Network Kanji Filter」の略

文字コードと改行コードを変換するためのコマンド
```
$ nkf [オプション] [ファイル]
$ nkf [オプション] --overwrite ファイル
```
