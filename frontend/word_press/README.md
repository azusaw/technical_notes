WordPressでどこまでできるのかを調査。

## やろうとしたこと
「Adobe XD」で作成したプロトタイプをどこまで再現できるか？
https://xd.adobe.com/view/cb11d38f-38d8-40c5-7510-1cb8c15dc4bb-bd20/

頑張ればいろいろできるのかもしれないけど、今回は画面操作だけで挑戦。

<br>

## 使用したプラグイン
#### テーマ
<img width="673" alt="image.png (201.7 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/78d1d0ce-955b-4155-ab71-1a039d0d7829.png">

今回は画像左の「<a href="https://colibriwp.com/?utm_source=install&utm_medium=wp">colibri</a>」を使用。

右の「OnePress」も評判が良いので使ってみましたが、直感的に操作ができないので諦めた。
テーマによって操作感、できることが大きく異なる印象。

#### フォント
Noto Sans JPを使用するために、「 Google Fonts typography」 をインストール。

<br>
<br>

##  ヘッダー、ヒーロー
 ▼ Adobe XD
<img width="1610" alt="image.png (2.7 MB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/cfa11fcb-b9bb-4c93-8893-7a3a95b01a4d.png">

▼ WordPress
<img width="1890" alt="image.png (3.3 MB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/9265a09f-c6bc-45a4-949e-4a97ac58a081.png">


### Good
- ボタンにカーソルををホバーするアニメーションが簡単につけられる
-  スクロールでヘッダーが浮き上がり、背景色が付く

### Bad
- ヘッダーの文字色の変え方が不明
- おそらくヘッダーにプルダウンメニューも入れられない？
- ユーザが入力可能なテキストボックスのフォームが用意されていない
- フォントサイズ、行間、文字間の指定ができない

### 感想
ロゴと背景以外一致しないんじゃないかというレベル。
ボタンについてもリンクしか貼れないので、検索などのしくみは自分で作らないといけない。

<br>
<br>

##  コンテンツ１：特徴紹介（アイコン＋テキスト）
▼ Adobe XD
<img width="1439" alt="image.png (98.4 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/f7fbd822-cc7e-4739-a7b6-5849759d7205.png">

▼ WordPress
<img width="1145" alt="image.png (65.1 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/6834dcbc-2042-4386-a029-258358c07853.png">



### Good
- アイコンの選択が簡単（種類は少ない）
- デザインのサンプルがある

### Bad
- ひとつひとつクリックして入力…を繰り返すのがやや大変

### 感想
ここはWordPressの方が素敵にできた。
コンテンツを追加するときにデザインが選べるので、赤い矢印のものを選択。
ただしほとんどのデザインはPro表記があり、有料プランでないと使えない。
無料のものは3個くらいしかない。

<img width="286" alt="image.png (90.4 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/88b1fb29-1785-4035-b0c3-bf56039f0976.png">


<br>
<br>

##  コンテンツ２：新着物件一覧（画像＋テキスト）
▼ Adobe XD
<img width="1552" alt="image.png (313.5 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/441bd488-3ff2-4d59-8bf1-bccb60d8601d.png">

▼ WordPress
<img width="1510" alt="image.png (247.1 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/703e9e37-a3b3-44b1-bb93-4c1310668412.png">



### Good
- なし

### Bad
- 各パーツの 入力が大変（画像のアップロード、文字の入力、文字色の変更、左寄せ指定を１つ１つ）
- 角を丸くできない

### 感想
CMSで作られたサイト特有のカクカク感は、かどをまるめられないからなのでしょうか？

また、デザイン時は、画像とテキストのセットをCardコンポーネントにする想定でしたが
WordPressでは以下のような組み合わせで作っています。

<img width="600" alt="image.png (283.3 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/e65b5b52-c8c1-4c9d-9c77-d1dcb3b555aa.png">


このとき、リンクが貼れるのがimageに対してだけなので、カードをクリックして詳細表示、みたいなことはできない。
（columnにリンクが貼れない）


<br>
<br>


##  コンテンツ３：エリアから探す（画像  ON テキスト）
▼ Adobe XD
<img width="1555" alt="image.png (1.0 MB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/e438d270-eec1-470f-81cf-1d95ded9759a.png">

▼ WordPress
<img width="1104" alt="image.png (186.6 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/21/79557/11209be1-46d2-4ac3-833b-27e2e90d6fe4.png">


### Good
- なし

### Bad
- 画像の上に文字が置けない
- 画像サイズの統一ができない（そろえるには、同じサイズの画像を用意する必要がある？）

### 感想
ボタンの入力は途中であきらめました。
ボタンおいて、文字入れて、スタイル指定して、を繰り返すのが大変…。

<br>

-------

## まとめ
### いいところ
- デザインのサンプルがあるので、デザインが思いつかない人向き
- 普通のウェブサイトをつくるぶんには十分パーツが揃っている
- アニメーションを簡単に入れられる

### ダメなところ
- パーツのコピペができない
- その結果、クリックして入力を繰り返すのでストレスがたまる
- 無料プランではデザインの自由度が低い

### 感想
あまり作りこんでないものの、ものすごくストレスがたまる。
画面の使いづらさ、繰り返し作業、自由が利かないことが多い 等

高度なカスタマイズは、CSSやPHPなどをいじれば書けばできるらしい。
また、パーツやページの使いまわしができないものかと調べたら、これもコードのコピペでやるらしい。
ソース書くのとあんまり変わらない。

今回使用したColibriも、有料プランならProデザインだけでなく
行間、文字間の調整やいろいろなアニメーションも使えるみたいなので
デザインの不自由さは減るかもしれない。
https://colibriwp.com/?utm_source=install&utm_medium=wp#pricing




