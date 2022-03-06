# Linux
## curl

## dig
ドメイン名からIPアドレスを調べる
結果を加工しないのでトラシューではdig推奨
```
$ dig www.google.com

google.com.             289     IN      A       74.125.193.100
google.com.             289     IN      A       74.125.193.138
google.com.             289     IN      A       74.125.193.113
google.com.             289     IN      A       74.125.193.101
google.com.             289     IN      A       74.125.193.139
google.com.             289     IN      A       74.125.193.102

$ dig -x IPアドレス で逆引き
```

## host
ドメイン名からIPアドレスを調べる
disの簡単版
```
$ host google.co.jp

google.co.jp has address 74.125.193.94
google.co.jp has IPv6 address 2a00:1450:400b:c01::5e
google.co.jp mail is handled by 0 smtp.google.com.
```

## nsloolup
ドメイン名からIPアドレスを調べる
非推奨
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
