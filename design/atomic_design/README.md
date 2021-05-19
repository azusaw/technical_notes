# Atomic Design
https://atomicdesign.bradfrost.com/chapter-2/

## 概要
パーツを細かい単位でデザインしていく手法。UI設計の考え方のひとつ。

細かい順に、
* Atoms（原子）
* Molecules（分子）
* Organisms（有機体）
* Templates（テンプレート）
* Pages（ページ）

![image](https://user-images.githubusercontent.com/72424558/118745327-e0211d00-b890-11eb-927b-8d3da4260c41.png)

大規模サイト作成やひな型作成には確かに便利そうではあるが、ここまで細かく分けると作るの大変そう。

-----

## 定義しておく
### Atoms
> If atoms are the basic building blocks of matter, then the atoms of our interfaces serve as the foundational building blocks that comprise all our user interfaces.

* 単体では機能しない
* プロダクトの情報を持たない
* フォーム、ボタン、ラベルなど。

### Molecules
> In interfaces, molecules are relatively simple groups of UI elements functioning together as a unit. For example, a form label, search input, and button can join together to create a search form molecule.

* いくつかのAtomsを組み合わせて構成される
* 単体では成立しない
* プロダクトの情報を持たない
* 検索ボックス、ラベル付きテキストボックスなど

### Organisms
> Organisms are relatively complex UI components composed of groups of molecules and/or atoms and/or other organisms. These organisms form distinct sections of an interface.

* いくつかのAtoms/Moleculesを組み合わせて構成される
* 単体で存在できる
* <b>プロダクトの情報を持つ</b>
* ヘッダー、フッター、入力フォーム全体など

Organismsはサイト名などが入っていて、ほかのプロジェクトでは流用できない単位になる。

データを持たせられるということなので、APIで取得した情報を持たせてもOK。

### Templates
> Templates are page-level objects that place components into a layout and articulate the design’s underlying content structure.

* いくつかのAtoms/Molecules/Organismsを組み合わせて構成される
* 単体で存在できない
* ページレイアウト

### Pages
> Pages are specific instances of templates that show what a UI looks like with real representative content in place. 

* 最終的に完成するページ





