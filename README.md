# OpenSnail


DiscordとScratchを連携する拡張機能

元リポジトリが動かないので改修工事しました。

## 機能

| ブロック名        | タイプ     | 動作                                   |
| ----------------- | ---------- | -------------------------------------- |
| authenticete user | スタック   | Discordのポップアップを開き認証        |
| username          | レポーター | Discordアカウントのユーザー名を取得    |
| profile picture   | レポーター | DiscordアカウントのアイコンのURLを取得 |
| authenticated?    | ブール     | Discordに認証済みか確認                |

アイコンはturbowarpの埋め込み系の拡張機能と組み合わせて使うといいよ！

## 手順

#### ①

[https://dashboard.render.com](https://dashboard.render.com)

RenderのダッシュボードからWeb Serviceを作成。

Build and deploy from a Git repositoryにチェックを入れる。

Public Git repositoryにこのGitHubのURLを貼る。

オプションなどは自由。無料版で問題ないよ。

アプリケーションのURLコピー。〇〇.onrender.comみたいなやつ。

#### ②

[https://discord.com/developers/applications](https://discord.com/developers/applications)

Discordアプリを作成。名前や設定は自由。

OAuth2を開く。

CLIENT IDとCLIENT SECRETをコピー。CLIENT SECRETは新しく作成します。

RedirectsにアプリケーションのURL+/auth/discord/callbackを貼る

例：https://〇〇.onrender.com/auth/discord/callback

#### ③

Renderの自分のアプリケーションのページに戻る。

Environmentを選び、先ほどコピーしたCLIENT_IDとCLIENT_SECRETとAPP_URLを設定。

こっちのAPP_URLはそのままでいい。

例：https://〇〇.onrender.com

#### ④

`discord-ext.js`をコピーしてメモ帳などに貼る。

37行目あたりの"Your app URL here"に自分のアプリケーションのURLに変更する。

例：https://〇〇.onrender.com

#### ④

[https://studio.penguinmod.com/editor.html](https://studio.penguinmod.com/editor.html)

[https://turbowarp.org/editor](https://turbowarp.org/editor)

拡張機能からカスタム拡張機能を選ぶ。

テキストタブに④で書き換えたコードを貼り付ける。

「サンドボックスなしで拡張機能を実行する」にチェックを入れる。入れなければ動かないよ！

#### ⑤

常時起動などがしたかったらUptimeとか別のサービスを使ってね。
