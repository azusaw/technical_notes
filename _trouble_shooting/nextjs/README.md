# Next.js

## 事象
#### 原因
#### 回避策
#### 修正前
#### 修正後
-----

## 初回レンダリング時にrouterがundefinedになる

#### 回避策
防ぎようがないので、undefinedでなくなったことを確認して読み込む

#### 修正前
```
 if (!(router.query.useId instanceof Object)) {
   setUserId(router.query.useId)
 }
```

#### 修正後
```
if (router.asPath !== router.route) {
  if (!(router.query.useId instanceof Object)) {
    setUserId(router.query.useId)
  }
}
```
-----

## レイアウト内のchildrenにpropsを渡せない

#### 回避策
childrenをcloneしつつ、パラメータを付け加える

#### 修正前
```
<div>
  {children}
</div
```

#### 修正後
```
<div>
  {React.cloneElement(children, { user: loginUser })}
</div
```
-----

## PWAに対応した後、Basic認証がUnauthorizedとなる

#### 原因
- PWA対応に必要なService WorkerとBasic認証の相性が悪い
- 認証情報のキャッシュが使われている

#### 回避策
- シークレットタブで開く
- 開発ツールの`Bypass for network`にチェックを入れる

-----
## ページ遷移時にページのトップに移動しない。

#### 回避策
useEffectを使用して、ページ遷移先の初回読み込み時にトップに移動させる。
```
useEffect(() => {
  window.scrollTo(0, 0)
}, [])
```
-----
## atnd-proのグラフ系コンポーネント使用したところ、ReferenceError: document is not definedエラーが発生。
 
#### 原因
- antdの内部で、ブラウザ上の変数である document を使用している
- Next.jsがSSRの挙動をしている
 
#### 回避策
Next.jsのDynamic Importを使い、SSRをfalseにする
 
#### 修正前（エラー発生）

```
import React, { useEffect, useState } from "react"
import Bar from "ant-design-pro/lib/Charts/Bar"
　　：
  return (
    <div>
      <Bar height={200} title="chart" data={data} />
    </div>
  )
}
export default ReportsPage
```
 
#### 修正後
```
import React, { useEffect, useState } from "react"
import dynamic from "next/dynamic"
const Bar = dynamic(() => import("ant-design-pro/lib/Charts/Bar"), {
  ssr: false,
})
　　：
  return (
    <div>
      <Bar height={200} title="chart" data={data} />
    </div>
  )
}
export default ReportsPage
```
