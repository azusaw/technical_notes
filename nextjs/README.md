# Next.js


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
