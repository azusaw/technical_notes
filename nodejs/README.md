# Node.js

## 事象
#### 原因
#### 回避策
#### 修正前
#### 修正後
-----
## 事象
以下のようなエラーでnpm installに失敗する
```
gyp ERR! configure error 
gyp ERR! stack Error: Command failed: /Users/jovan/anaconda3/bin/python -c import sys; print "%s.%s.%s" % sys.version_info[:3];
gyp ERR! stack   File "<string>", line 1
gyp ERR! stack     import sys; print "%s.%s.%s" % sys.version_info[:3];
gyp ERR! stack                                ^
gyp ERR! stack SyntaxError: invalid syntax
gyp ERR! stack 
gyp ERR! stack     at ChildProcess.exithandler (child_process.js:294:12)
```
  
#### 原因
使用しているAnaconda3はPython3.xであるが、node-gypはPython2.7の想定で動いているため。
```
# Python2.7
import sys; print "%s.%s.%s" % sys.version_info[:3];

# Python3.x
import sys; print("%s.%s.%s" % sys.version_info[:3]);
```

#### 回避策
- Anaconda3をアンインストールし、Ptyhon2.7をインストールする
- [windows-build-tools](https://github.com/felixrieseberg/windows-build-tools)をインストールする

-----
## 事象
↑の対処でPython2.7系を入れたが、npm installに失敗する
```
Warning: unrecognized setting VCCLCompilerTool/MultiProcessorCompilation
Warning: unrecognized setting VCCLCompilerTool/MultiProcessorCompilation
このソリューション内のプロジェクトを 1 度に 1 つずつビルドします。並行ビルドを有効にするには、"/m" スイッチを追加してください。
MSBUILD : error MSB3428: Visual C++ コンポーネント "VCBuild.exe" を読み込めませんでした。この問題を解決するには、次のいずれかを行ってください。 1) .NET Framework 2.0 SDK インストールする
。 2) Microsoft Visual Studio 2005 をインストールする。 3) その他の場所
にインストールされている場合、コンポーネントの場所をシステム パスに追加する。 [C:\work\study\vue\mahjong_score_calclation\node_modules\fibers\build\binding.sln]
gyp ERR! build error 

```
  
#### 原因
node-gypが必要としているC++のパッケージが見つからないため。

#### 回避策
- Visual Studio 2015/2017をインストールする
