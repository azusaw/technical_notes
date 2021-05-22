# 画像の保存形式について
webサイト作成で様々な画像の形式があることを知り、「どの形式で保存するのが最適か？」を調べたのでまとめる。

## 形式の種類と特徴
### JPG（じぇいぺぐ）
 *  1,677万色
 * 不可逆圧縮（大きいデータをとても小さくできるが、復元不能）
 *  加工 ⇒ 保存を繰り返すと、保存時に圧縮処理が行われるため画質が荒くなる
 *  ファイルサイズが小さい
 * フルカラー写真向け
 
### PNG（ぴんぐ）
* PNG-8（256色）、PNG-24（1,677万色）、PNG-32（1,677万色 + 透過 = 280兆色）がある
*  可逆圧縮
*  透過色を使用できる
* ファイルサイズが大きい
*  アイコン、ロゴ向け

### GIF（じふ）
* 256色
*  可逆圧縮
* 透過色を使用できる
*  ファイルサイズが小さい
*  アイコン、アニメーション向け

### SVG（えすぶいじー）
* JPG/PNG/GIFの「ラスタ形式」と異なり、**「ベクトル形式」**（PDFと同じ）
*  拡大、縮小をしても画像が荒れないので、レスポンシブデザインに最適
* CSSでスタイル指定できるので、後から編集がしやすい
*  IllustratorやPhotoshopなどのソフトが必要
*  アイコン、ロゴ向け
  
  
## 比べてみよう
<img width="300" alt="business_consulting.png (25.6 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/15/79557/d479cb6a-6734-4da2-82b2-1f39bf5d02f0.png">

この画像は**PNG-32**で作成しています。（ファイルサイズ  33.2KB）
これを**JPG**で保存してみる。

<img width="300" alt="business_consulting.jpg (27.7 KB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/15/79557/86d7ffc2-8d0d-42e4-b261-576b0adf6afa.jpg">

ファイルサイズは27.8KBと、**JPGよりPNGが5.5KB大きくなりました。**
PNGは背景が透過されています。（クリックするとわかる）

- - -  
<img width="500" alt="president.jpg (75.6 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/15/79557/2e806d35-49f2-4188-b53a-a72062a0caf9.jpg">

次はこの画像、**JPG**で作成しています。（ファイルサイズ75.6KB ）
これを**PNG-32**にすると…

<img width="500 " alt="president.png (912.8 kB)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/15/79557/39e6f78b-81e1-483b-8a63-92e9cc1b7e9a.png">

見た目は同じですがファイルサイズは912.8 KBと、**PNGがJPGより10倍以上大きくなりました！**

このようにPNGはフルカラーだと驚異的に重くなるので、**写真はJPG、アイコンはPNG**という方針で画像を作成していました。
GIF形式は自分のお絵かきソフトに対応していなかったので、残念ながら試せていない。

- - -
さいごにSVG。
もともとのサイズであるwidth=24だとこんな感じです。

<img width="24" alt="iconmonstr-file-4.svg (289 B)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/15/79557/1a7bd8a2-a522-4622-80c9-2bde7f6ac8f5.svg">

これをwidth=400にしてみると…

<img width="400" alt="iconmonstr-file-4.svg (289 B)" src="https://img.esa.io/uploads/production/attachments/15173/2020/04/15/79557/1a7bd8a2-a522-4622-80c9-2bde7f6ac8f5.svg">

めくれてる部分がなめらかできれい。
しかもファイルサイズは、なんとわずか**298B**！

.svgファイルをテキストエディタで開くと、XML形式で情報が書かれている。

```
<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
    <path d="M14.568.075c2.202 1.174 5.938 4.883 7.432 6.881-1.286-.9-4.044-1.657-6.091-1.179.222-1.468-.185-4.534-1.341-5.702zm-.824 7.925s1.522-8-3.335-8h-8.409v24h20v-13c0-3.419-5.247-3.745-8.256-3z"/>
</svg>
```

## まとめ

写真はJPG。
単色系アイコンは**SVG**。
SVG形式で素材を作れば、軽いうえにサイズ調整ができるので、いろいろな部分で使えそう。





