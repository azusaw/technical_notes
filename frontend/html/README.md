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
  
### head
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

#### meta
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
  
### body
```
section
├─ <section> 1つのまとまり（セクション）
├─ <nav>　　  メニューなどのナビゲーション
├─ <article>  記事
├─ <aside>  　余談、補足情報
├─ <header>
├─ <footer>
└─ <address>  連絡先
 
```
