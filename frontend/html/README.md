# html

## 基本
```
<html>
  <head>
    <title />
     :
  </head>
  <body>
     :
  </body>
</html>
```

### html
Hyper Text Markup Language<br />
HTMLですよのサイン<br />
直下には<head><body> or <head><frameset> しか置けない

### head
作者情報、サーチエンジン向けのキーワードや説明、文書のタイトル、利用するスタイルシートなどを記述する<br />
`<title>`で指定する文書のタイトル以外のほとんどの情報は ブラウザ上には表示されない

### body
実施に画面に表示する内容を書く

----
  
## head
```
head
├─ <title>  検索結果やブックマーク名として使用される言葉
├─ <base>   相対パスの基準URIを指定（href or target）
|　　　　　  絶対パスでリンクを書くならいらない要素
├─ <link>   使用する外部リソースのリンク（HTML、CSS、RSSなど）
|　　　　　  href or rel 属性が必須
├─ <style>  文書全体のスタイルを指定
├─ <script> 使用するスクリプト言語を宣言（language=Javascript など）
└─ <meta>   文書に関するメタデータを指定
```

### meta
`<meta name="xxxx" content="xxxxxxxxx">` の形で様々な情報を指定する
  * keywods: 検索エンジンにインデックス用キーワードを与える
  * description: 文書の説明 検索エンジンに使用されるので注意
  * authur: 作者名
  * robots: クロールさせたくないときに指定
  * application-name: ウェブアプリケーション名 ※ webサイトなら指定不可
  
例
```
  <meta name="keywords" content="azsaw, react, website">
  <meta name="description" content="azusaw"のウェブサイトです。">
  <meta name="robots" content="noindex, nofollow">
```

----
                                                 
## body
```
section
├─ <section> 1つのまとまり（セクション）
├─ <nav>　　  メニューなどのナビゲーション
├─ <article>  記事
├─ <aside>  　余談、補足情報
├─ <header>
├─ <footer>
└─ <address>  連絡先

content
├─ <p> 　 段落（パラグラフ）
├─ <hr>　 テーマや話題の区切り
├─ <pre>  半角スペースや開業をそのまま表示
├─ <blockquote> 引用、転載
├─ <ol> 　番号つきリスト
├─ <ul> 　番号なしリスト
├─ <li> 　リスト項目
├─ <dl>　 定義、説明リスト
├─ <dt>　 定義、説明リスト項目
├─ <dd>   定義用語や言葉の説明
├─ <figure> 　  図表
├─ <figcaption> 図表のキャプション
├─ <div>   ひとかたまり 
└─ <main>  メインコンテンツ

embedded
├─ <img> 　 　画像
├─ <iframe>　 インラインフレーム（別のHTMLのコンテンツを埋め込む）
├─ <embed>  　プラグインデータ（Flashなどプラグインが必要な奴はこっちで埋め込む）
├─ <object> 　外部リソース
├─ <param>    プラグインのパラメータ
├─ <video> 　 動画
├─ <audio> 　 音声
├─ <source> 　動画や音声などのURLや種類を指定
├─ <canvas>　 図形を描く
├─ <map>　　　イメージマップ（画像の特定領域に、任意の形でリンクを置いたもの）
└─ <area>  　 イメージマップのハイパーリンク指定

form
├─<form> 　   フォーム
├─ <label>　  フォーム部品（input）と項目名（ラベル）を関連付け
├─ <input>    フォームの部品
├─ <button>   ボタン
├─ <select>   セレクトボックス
├─ <datalist> 入力候補を提案（選択もできるし、テキスト入力もできる）
├─ <option>   セレクトボックスなどの選択肢
├─ <optgroup> 選択肢をグループ化
└─ <progress> 進行状況
```

### input
`<input type=xxxx>`次第で様々な入力フォームになる
* text: 1行のテキスト      
* search: 検索ボックス
* tel: 電話番号
* url: URL
* email: メールアドレス
* password: パスワード
* datatime: 日時
* date:  日付
* month: 月
* week: 週
* time: 時間
* number: 数値
* range: 範囲
* color: 色
* checkbox: チェックボックス
* radio: ラジオボタン
* file: ファイル
* submit: 送信ボタン
* image: 画像ボタン
* reset: リセットボタン

`<input xxxx>`のように直接あてる属性
* autofocus: 自動フォーカス
* placeholder: プレースホルダー
* patterm: 正規表現
* min max: 入力可能な最大、最小
* step: 入力で刻むステップ
* autocomplete: 自動補完
* multiple: 複数選択可能
