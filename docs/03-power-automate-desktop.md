# Power Automate Desktop のフローを作ろう

![image](https://i.gyazo.com/804c11e55ae9847e7f892fdcc1c9506e.png)

enebular editor から Power Automate Desktop でデータを受け取って Excel に保存するところを説明します。

## Power Automate Desktop とは

![image](https://i.gyazo.com/5131a17bd13719baf76bef578741b1ea.png)

Power Automate Desktop は、デスクトップと Web の操作をドラッグアンドドロップのフローを作って自動化するツール。

今回の Power Automate Desktop は無償版で進めます。Windows 10 に無償で手軽に入れれるけど、有償版と違って、作成したフローの共有やクラウド版 Power Automateサイトとの連携、接続クラウドフローとの連携による自動実行ができませんが、外部から受け取ったデータを Excel に保存するような流れは得意です。

それでははじめてみましょう。

## アプリを開きます

![image](https://i.gyazo.com/eb059cc05ee35ed0210f6e1ebd22bf71.jpg)

Power Automate Desktop でデスクトップ フローを作成するには、アプリを開きます。

![image](https://i.gyazo.com/7aca9c4d0f36cd5777d5fe058602a658.jpg)

右上の 新規フロー を選択します。

![image](https://i.gyazo.com/e432bae279640e08d0496f554a0aecce.jpg)

フローを作成する画面でフロー名を決めます。

![image](https://i.gyazo.com/bc57e9900087fd95f8667be337f9c04f.jpg)

`enebular x PAD` という名前にして、作成ボタンをクリックします。

![image](https://i.gyazo.com/4b053f37eb4670f6430a00cc13f3b037.jpg)

フローがリストに登場します。

![image](https://i.gyazo.com/63776702a8c8796907fa575d74c98a10.jpg)

フローエディタが表示されます。

## 「Web サービスを呼び出す」アクションを探します

![image](https://i.gyazo.com/7dd40d03d64313b61a459d72bcaae1b2.png)

右側のアクションから Web のグループを探します。

![image](https://i.gyazo.com/7dd40d03d64313b61a459d72bcaae1b2.png)

クリックして詳細を表示します。

![image](https://i.gyazo.com/ab1129ce659c84b29b689605632a5bfb.png)

各アクションのタイトルが全部表示されておらず見にくい場合があるので、

![image](https://i.gyazo.com/7aee10493a77cf4b53d477527b303635.png)

広げましょう。

「Web サービスを呼び出す」アクションをフローエリアにドラッグアンドドロップしましょう。

## 「Web サービスを呼び出す」アクションの設定をする

「Web サービスを呼び出す」アクションの設定をします。

![image](https://i.gyazo.com/4f30c47e2656aeb2147ad72125272c08.png)

- URL
  - http://localhost:1888/api
- メソッド
  - GET
- 受け入れる
  - application/json
- コンテンツタイプ
  - application/xml

設定できたら、保存ボタンをクリックします。

## 一度、保存します

フロー全体が表示されたら、一度、保存しましょう。

![image](https://i.gyazo.com/7900f43e357a38f376b6decad093f7b4.png)

保存ボタンをクリックします。

## 「JSON カスタムオブジェクトに変換」アクションを追加

![image](https://i.gyazo.com/a33028c794cf1d2c5c2138689a88e71d.png)

変数 > JSON カスタムオブジェクトに変換 アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/cdee750c528bd3cb405289a6dddc2f45.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

![image](https://i.gyazo.com/2461daa854dfccda9fc5e7ce70cd267f.png)

`{x}` のボタンを押して変数の選択をします。

![image](https://i.gyazo.com/74e3326a50fac4db6ba169c7d4774fab.png)

`WebServiceResponse` をクリックして選択します。

![image](https://i.gyazo.com/48bb135f1129006be6156cde8067ac8e.png)

JSON のテキストエリアに `%WebServiceResponse%` という文字が追加されます。

![image](https://i.gyazo.com/322980dd0cf07ebd20023532785bdb15.png)

保存ボタンをクリックして、アクションの設定を反映します。

## Excel ファイル sample.xlsx の準備

[こちらのsample.xlsx](https://docs.google.com/spreadsheets/d/1Fl9aKuS5QRvD0soGanWiTIhoYKphfOsP/edit?usp=sharing&ouid=104272198193143899688&rtpof=true&sd=true) をデスクトップにダウンロードします。

あるいは、Excel でセルが空の状態のまま新規作成したファイルを sample.xlsx で保存いただいて使っていただいてもOKです。

## 「Excel の起動」アクションを追加します

![image](https://i.gyazo.com/17d3286d3750ddfd6cef0778f2caef28.png)

Excel > 詳細 > Excel の起動 アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/2eccdeb1ce201d3d95f3bc0f9dc1c682.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

![image](https://i.gyazo.com/b306ffdbd876907929d4dbb3d6e8fc35.png)

Excel の起動の欄を `次のドキュメントを開く` を選択します。

![image](https://i.gyazo.com/a07de8c24532cb51287418459efc51d6.png)

ドキュメントパスのファイルを選択アイコン（赤枠）をクリックします。

![image](https://i.gyazo.com/7b139e8581a3e8a0c5482fc11b7b6441.png)

ファイルの選択ダイアログが表示されるので、先ほどの `sample.xlsx` を選択して、開くボタンをクリックします。

![image](https://i.gyazo.com/e6428f12377cf0e9354595a1b7641484.png)

アクションの設定画面に戻ったら、

![image](https://i.gyazo.com/322980dd0cf07ebd20023532785bdb15.png)

保存ボタンをクリックして、アクションの設定を反映します。

## 「変数の設定」アクションを追加します

![image](https://i.gyazo.com/9d692eb02d38eb7ce13755dfe51d8112.png)

変数 > 変数の設定 アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/6af59c6f4a4ec02a753369db7b71f532.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

![image](https://i.gyazo.com/e89328d3d88c07b5c97f1732690d2db3.png)

設定の NewVar の部分をクリックします。

![image](https://i.gyazo.com/93007f17fe00f9d4c9c19ce939cdffc5.png)

%NewVar% というテキストを、

![image](https://i.gyazo.com/460569aaa5dcd0317ff61e67dc851885.png)

`%CurrentCount%` というテキストに変更します。

![image](https://i.gyazo.com/c38707c0d2de0ffe21950d312369776b.png)

宛先に半角の 1 を入力します。

![image](https://i.gyazo.com/57103697d986b64bcf08e5117eaa511b.png)

設定できたら、保存ボタンをクリックして、アクションの設定を反映します。

## 「For each」アクションを追加します

![image](https://i.gyazo.com/dbc4b7135e6da90476640576950cee68.png)

ループ > For each アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/f06254fdf7bbc139760cc01c9a23b500.png)

さきほどの「変数の設定」アクションの下部に載せてラインが表示されたらドロップして配置します。

![image](https://i.gyazo.com/130b18c5deafdafd11ba9c7f7dad1db4.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

パラメータを以下のように設定します。

* 反復処理を行う値
  * `%JsonAsCustomObject['datas']%`

設定できたら、

![image](https://i.gyazo.com/43223ad5a11c6a0646d862e9083c37c1.png)

保存ボタンをクリックして、アクションの設定を反映します。

## 「Excel ワークシートに書き込み」アクションを追加します その1

![image](https://i.gyazo.com/665a255341ac89fc5a72074b7cf9b0e8.png)

Excel > 詳細 > Excel ワークシートに書き込み アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/aeea19a3af2de90ead3835909e05d8ef.png)

For each アクションの End の上部に載せると、間に入れる案内としてラインが表示されたらドロップして、For each と End の間に配置します。

![image](https://i.gyazo.com/d04fb204d2c499964c0f69d13a0e9590.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

![image](https://i.gyazo.com/96f38e39520b9fb97e904dbbaa44c1f2.png)

パラメータを以下のように設定します。

* Excel インスタンス → そのまま
  * `%ExcelInstance%`
* 書き込む値
  * `%CurrentItem['col1']%`
* 書き込みモード
  * 指定したセル上 → そのまま
* 列
  * 1
* 行
  * `%CurrentCount%`

設定できたら、

![image](https://i.gyazo.com/322980dd0cf07ebd20023532785bdb15.png)

保存ボタンをクリックして、アクションの設定を反映します。

## 「Excel ワークシートに書き込み」アクションを追加します その2

![image](https://i.gyazo.com/665a255341ac89fc5a72074b7cf9b0e8.png)

Excel > 詳細 > Excel ワークシートに書き込み アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/1000eef43f8ca63bf7a8a5863023f4b9.png)

さきほどの「Excel ワークシートに書き込み」の下部に載せてラインが表示されたらドロップして、先ほどのアクションと End の間に配置します。

![image](https://i.gyazo.com/d04fb204d2c499964c0f69d13a0e9590.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

![image](https://i.gyazo.com/dd488fbe23058f2f7334f83ccedc1ccc.png)

パラメータを以下のように設定します。

* Excel インスタンス → そのまま
  * `%ExcelInstance%`
* 書き込む値
  * `%CurrentItem['col2']%`
* 書き込みモード
  * 指定したセル上 → そのまま
* 列
  * 2
* 行
  * `%CurrentCount%`

設定できたら、

![image](https://i.gyazo.com/322980dd0cf07ebd20023532785bdb15.png)

保存ボタンをクリックして、アクションの設定を反映します。

## 「変数を大きくする」アクションを追加します

![image](https://i.gyazo.com/4c0b58337cebd89fbf372fc39749dba4.png)

変数 > 変数を大きくする アクションをドラッグアンドドロップで追加します。

![image](https://i.gyazo.com/1b054548c29ff5b9d2bc6f6c8838f252.png)

さきほどの「Excel ワークシートに書き込み」の下部に載せてラインが表示されたらドロップして、先ほどのアクションと End の間に配置します。

![image](https://i.gyazo.com/189c76d01452a9232521b33e275a9756.png)

ドラッグアンドドロップするとアクションの設定画面が表示されます。

![image](https://i.gyazo.com/15335f974ac30f0b14d830109ef913ce.png)

パラメータを以下のように設定します。

* 変数名
  * `%CurrentCount%`
* 大きくする数値
  * 1

設定できたら、

![image](https://i.gyazo.com/322980dd0cf07ebd20023532785bdb15.png)

保存ボタンをクリックして、アクションの設定を反映します。

## 最後にフローを保存する

![image](https://i.gyazo.com/79b9acbb9ccd7fe031893f1054868c1e.png)

フロー全体を確認できたらフローを保存しましょう。

![image](https://i.gyazo.com/b2cce7b71580e648eb765fe15b7f7905.png)

保存ボタンをクリックします。

## 次は

お疲れ様でした。

左のメニューから次のコンテンツ「いよいよ動かしてみよう」をクリックしましょう。