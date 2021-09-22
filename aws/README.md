# AWS

## Amplifyにカスタムドメインを設定
### Route53へドメインを移行
これが出来れば、Route53のドメイン選択とネームサーバを移行するだけで設定が完了する。
ただし".co.jp"ドメインは移行不可。

### SSL認証
お名前.comのDNSレコードを編集
```
_xxxx.my-domain.co.jp CNAME _xxxxxxxxx.xxxxxxxxx.acm-validations.aws
```

### CNAMEの設定
次にAレコード(Alias)とCNAMEをお名前.comのDNSレコードに登録する必要があるが、
お名前.comでAレコードはサポートしていないため設定が不可能だと判明。

### どうするか
以下の方針に変更。
* Route53にホストゾーンを作成し、今まで設定したDNSレコードの内容を移行
* お名前.comではほかのネームさーん場を使用するように設定

最終的なレコードは以下。
```
# Aliasレコード
my-domain.co.jp	A	シンプル	-	
xxxxxxx.cloudfront.net.

my-domain.co.jp	NS	シンプル	-	
ns-xxxx.awsdns-xx.co.uk.
ns-xxxx.awsdns-xx.net.
ns-xxxx.awsdns-xx.org.
ns-xxxx.awsdns-xx.com.

my-domain.co.jp	SOA	シンプル	-	
ns-xxxx.awsdns-xx.co.uk. awsdns-hostmaster.amazon.com. 1 7200 900 1209600 86400

# Search Console
my-soft.co.jp	TXT	シンプル	-	
"google-site-verification=xxxxx8"

_xxxxxxxx.my-domain.co.jp	CNAME	シンプル	-	
_xxxxxxxx.xxxxxx.acm-validations.aws.

www.my-domain.co.jp	CNAME	シンプル	-	
xxxxxxx.cloudfront.net
```

### 問題点
今回は未使用ドメインのため、ネームサーバをまるまるRoute53に転送することで対処できた。
使用中ドメインの場合は、外部のDNSサーバに設定をしていく方が良さそう。
お名前.comにはなかったものの、ムームードメインはAliasをサポートしている模様。

