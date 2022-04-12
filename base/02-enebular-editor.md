# enebular editor でフローを呼び出そう

![image](https://i.gyazo.com/484380c5cf099c600aaf0ff723bb91fa.png)

enebular editor (Node-RED) の部分を立ち上げます。

## なぜ Node-RED を使うのか

![image](https://i.gyazo.com/4dab36a711148421d554751aa4eff273.png)

Node-RED は IoT など様々なAPI/Data連携をGUIで直感的に構築できるオープンソースソフトウェアです。

![image](https://i.gyazo.com/df892be7beec10a38f3ffcee6297016e.png)

![image](https://i.gyazo.com/49f7d1782fce3c81aa7a19e3aa5426c0.png)

WEB まわりで使われる HTTP ノードもありAPI のデータ取得後のデータ加工についても、いろいろな標準ノードがあり Power Automate Desktop に扱いやすいデータをしやすい。

## なぜ enebular editor を使ったか

![image](https://i.gyazo.com/f831be9532fa2a8157bc601c52a60e38.png)

enebular を使うと他の人のフローを共有出来たりenebular editor ですぐ Node-RED を使える。複数ユーザーで開発（フロー共有）したり運用面を包括的に支援するプラットフォーム。

Node-RED のインストールは手軽とはいえ、Node.js や npm が必要だったり手間はかかるので、すぐに使える環境を enebular editor で使えるのは強み。

## プロジェクトを作成します

![image](https://i.gyazo.com/6f6cba0365810adf2397ffefbd91240d.png)

enebular にログインして Create Project ボタンをクリックします。

![image](https://i.gyazo.com/b43e92bc73f05223cf4ad9f2404b426b.png)

`handson-202109` という名前を入力して Submit ボタンをクリックします。

![image](https://i.gyazo.com/cd7544ce8a49cc5e42978fc0d203265e.png)

作成されてプロジェクトのリストに表示されました。

## Discover Flow から今回のフローをインポートする

![image](https://i.gyazo.com/8c020a30b2f933377423767b595d1a89.png)

今回の使うフローを Discover Flow で表示します。 → [今回のフロー](https://enebular.com/discover/flow/ef829af6-e61c-4e2c-8544-4bae73efe937)

![image](https://i.gyazo.com/6a36823dd6d12de62b88b1efba895551.png)

Import ボタンをクリックします。

![image](https://i.gyazo.com/bae03cdc125e4292c938c5763b9aeec4.png)

Importing Destination というウィンドウが表示されてインポート先が聞かれます。

![image](https://i.gyazo.com/c6f28446459147219b3f15b7a309f868.png)

* Project
  * さきほどの `handson-202109`
* Privilege 権限
  * edit, deploy, publish のまま

で設定して、Import ボタンをクリックします。

![image](https://i.gyazo.com/de325cba5d79f8777a9b2eb1437639dc.png)

インポートされました。これで準備は完了です。

## enebular editor を起動

![image](https://i.gyazo.com/35c38ff126f672e70060dd47256b1016.png)

enebular editor を起動します。

## インポートしたフローを選択

![image](https://i.gyazo.com/94a6452ed28ec15e2940ad752bd371a8.png)

プロジェクトリストからインポートしたフローを選択します。

![image](https://i.gyazo.com/46f063661f4943e93f10a2a50ba8bbed.png)

`enebular-pad-sample-01` の行のデスクトップというアイコンをクリックします。

![image](https://i.gyazo.com/eeedeae0c9e7c18431a854300be07f2b.png)

読み込みを待ちます。

![image](https://i.gyazo.com/776e8a94daef7ea36e03cb41a4cbfac5.png)

フローが表示されました。

## enebular editor の動作を確認する

Power Automate Desktop と連携する enebular editor のデータの入口（HTTP in）をブラウザで確認しましょう。

`http://localhost:1888/api`

こちらのアドレスを

![image](https://i.gyazo.com/4bdaf72650c8da7c47ae93906eccb74b.png)

Chrome ブラウザのアドレス欄に入力して、アクセスしてみましょう。

![image](https://i.gyazo.com/dc991970f05e654f2f68fbcb426315f9.png)

このように、アクセスできデータが取得出来たら、enebular editor の動作確認は完了です。

## こちらのデータは何か？

![image](https://i.gyazo.com/ece868783ed9c3db7cf069e981491159.png)

ユーロから他の通貨に替えるときの今日のレートをAPIから取得して、このあと使う Power Automate Desktop が扱いやすいようなデータに調整しています。

![image](https://i.gyazo.com/c965e4ab53721708e38cb8d52130c404.png)

col1, col2 がそのまま Excel のセルに入るようにしています。

## 次は

お疲れ様でした。

左のメニューから次のコンテンツ「Power Automate Desktop のフローを作ろう」をクリックしましょう。