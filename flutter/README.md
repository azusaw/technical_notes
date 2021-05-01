# Flutter開発環境構築

## Windows PC 🖥️

#### 開発キットをダウンロード
https://flutter.dev/docs/get-started/install/windows

#### 環境変数の追加
コマンドを使えるようにするため
`flutter\bin` のパスをフルパスを追加する

#### Flutterが使用できるかの確認
`fultter doctor`で必要な関連ライブラリが入っているかをチェックする

`Android license status unknown.` が表示された場合は、`flutter doctor --android-licenses` を実行

Java11で↑を実行した場合に以下のエラーが発生

```Exception in thread "main" java.lang.NoClassDefFoundError: javax/xml/bind/annotation/XmlSchema```

　-> Java8（Andoroid Studio標準）にすることで解決する


#### 「Windows ハイパーバイザープラットフォーム」をONにする
Windowsの機能の有効化から設定

## For Android 📱

#### Android Studio をPCにダウンロード
https://developer.android.com/studio
JetBrainsToolBoxからインストールできる

#### スマホの開発者向けオプションを設定
https://developer.android.com/studio/debug/dev-options

#### Google USB Driverをインストール
https://developer.android.com/studio/run/win-usb

#### Androidエミュレータの有効化
https://developer.android.com/studio/run/emulator-acceleration

## Andoroid Stutdio

#### Flutter Pluginのインストール
起動後、[Configlation]-[Plugins]からインストール

#### Flutterプロジェクトを作成
Android Studio再起動後、FlutterアプリをCreateする

#### AVD Managerの設定
[Tools]-[AVD Manager]




