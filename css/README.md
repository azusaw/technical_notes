# CSS

## ReactでSVGアニメーションコンポーネントを作成

### 1.SVG画像を作成

無料ソフト**InkScape**を使用。
<br />
このときテキストを「パスに変換」し、「ストローク（縁取り）」を作成すると、文字を縁取るアニメーションを作成することができる。

![image](https://user-images.githubusercontent.com/72424558/111892721-416b7200-8a41-11eb-84a6-8d3bcf75f01a.png)

### 2．アニメーションを作成

**SVG ARTISTA** を使用。
<br />
https://svgartista.net/
<br />
こちらのツールに先ほど作成したSVG画像をアップ。
<br />
[GET CODE]よりSVGとCSSコードを取得。

![image](https://user-images.githubusercontent.com/72424558/111892813-03bb1900-8a42-11eb-9c3d-4dd94dd1f2c9.png)

### 3. SVGコードをJSX形式に変換

**HTML to JSX Compiler** を使用。
<br />
https://magic.reactjs.net/htmltojsx.htm
<br />
コピーしたSVGコードはこのままJSXコンポーネントに使用できないが、このツールが`class` -> `className` のようにJSX形式に変換してくれる。

### 4. 不要なタグを削除

変換したコードをJSXに貼り付けるとエラーが出るので、Inkscape用のメタタグなどはすべて削除。
<br />
これでようやくSVGコンポーネントとして使用することができる。
