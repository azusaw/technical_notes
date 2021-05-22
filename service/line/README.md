# LINE連携メモ

## LINEでログイン
ただただログインしたいときに使う。
#### 必要なもの
* LINE アカウント
* LINE Developers アカウント （LINEアカウントをDevelopersにする）

#### 使うサービス
 * LINE Developers 

以下サイトがわかりやすい。
https://qiita.com/kakakaori830/items/4d54d012ff4ebf10c173

## LINEでログイン かつ 公式アカウントと友達になる
公式アカウントとメッセージのやり取りをしたい場合。
#### 必要なもの
* 上のLINEログインで必要なもの
* 上のLINEログインで作成したプロバイダ、チャネル
* LINE公式アカウント

#### 使うサービス
* LINE Developers
* LINE Official Account Manager

以下サイトがわかりやすい
https://manual.linestep.net/channelsetting
https://qiita.com/nkjm/items/c8eac296dfee14fe5cf7

チャネルと公式アカウントを連携させて、認証APIに```bot_prompt=aggressive```を追加すると、
ログイン処理と同時に、ログイン者のLINE友達に公式アカウントが追加される
メッセージ送信に使うトークンは「チャネルアクセストークン」なので注意（←はまった）


## 友だちをタグで分類＋タグで絞り込んで配信
#### 必要なもの
* LINE公式アカウント
#### 使うサービス
* LINE Developers
* LINE Official Account Manager

#### 手順
1. LINE Official Account Managerでタグを作成する
1. 作成したタグをもとにLINE Official Account Managerで**オーディエンス**を作成する
1. オーディエンスIDとチャネルトークンを指定してナローメッセージ配信 

※ タグ作成 ⇒ タグでオーディエンス作成の二段階が必要。
※ オーディエンス作成後にタグ付された友だちも、配信対象となる

----
#### オーディエンスとは？
以下の4タイプから作成可能
* ユーザIDアップロード（友達を指定したファイルをアップ）
*  クリックリターゲティング（過去に配信したメッセージに含まれるリンクをクリックしたユーザーを対象）
*  インプレッションリターゲティング（過去に配信したメッセージを開封したユーザーを対象）
* チャットタグオーディエンス（チャットタグごと）
* 友達追加経路オーディエンス（特定の経路で友達追加）

※ チャットタグ、友達経路追加オーディエンスはAPIから作成ができない
https://chat.line.biz/api/v1/bots/U653061f5c79f9019f04bcd4e8e21d613/contacts/U8905a5e98ff15544ea30f17343b8dcfc/tags/af2u6auxzzzsvt3vbgkjqz2hae

chat.line.biz/api/v1/bots/?channel?/contacts/UserID/TagID APIこんな感じ？
