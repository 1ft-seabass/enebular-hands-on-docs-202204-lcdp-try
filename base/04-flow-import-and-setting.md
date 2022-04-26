# フローをインポートして設定しよう

## フローをインポート

今回使う Twitter + AirTable 実行環境のフローを Discover Flow から持ってきます。

![image](https://i.gyazo.com/76a54b2d030f3bf8f63f7bfff033e61d.png)

上部のメニューから Discover Assets をクリックします。

![image](https://i.gyazo.com/bf3378203cf9c8bbd8fa48d8698e82ec.png)

検索で `handson-lcdp-try-202204-sample` で検索します。

![image](https://i.gyazo.com/a5dd09d3172319c27078bf6f8b4a84c7.png)

こちらをクリックします。もし検索でうまく見つからない場合は、こちらの [リンク](https://enebular.com/discover/flow/db0d7cf5-fb99-4a81-a23b-1a32655b22f7) からで直接アクセスできます。

![image](https://i.gyazo.com/783687d0e07e125f4ba13499ef2cd619.png)

インポートボタンをクリックします。

![image](https://i.gyazo.com/1aee078fb95be7e0bfc80678d8221725.png)

インポート先ウィンドウが表示されるので、プロジェクトを先ほど作成したプロジェクト名に設定して、インポートボタンをクリックします。

![image](https://i.gyazo.com/7525befb84b02360559d8da2fe233121.png)

これでインポートされました。

## エディタを開いて設定します

![image](https://i.gyazo.com/7faa3d09c375bc94674db55b1c808079.png)

編集ボタンをクリックして WEB エディタを開きます。

## おおまかな仕組み

![image](https://i.gyazo.com/0206da1fa598541ac51f532069cbab6a.png)

この部分は Twitter API v2 でのツイート取得する部分です。

[Twitter API v2 でのツイート定期取得を enebular 実行環境で試す | enebular blog](https://blog.enebular.com/samples/twitter-api-v2-%E3%81%A7%E3%81%AE%E3%83%84%E3%82%A4%E3%83%BC%E3%83%88%E5%AE%9A%E6%9C%9F%E5%8F%96%E5%BE%97%E3%82%92-enebular-%E5%AE%9F%E8%A1%8C%E7%92%B0%E5%A2%83%E3%81%A7%E8%A9%A6%E3%81%99/)

の仕組みを活用しています。

![image](https://i.gyazo.com/b4d214024bd8f69bf5837abce39f21a2.png)

この部分は、ツイートの件数によって、何かツイート取得出来れば Airtable に書き込むか、0件の場合は、すぐに LCDP ノードで返答することで実行を終了させています。

![image](https://i.gyazo.com/a43ec4a8d6f1d74d2e4f3917b03f50c5.png)

この部分は、Airtable でツイートを保存する部分です。

[スプレッドシートのようにデータ管理できる AirtableをNode-REDノードでデータを書き込んでみる | enebular blog](https://blog.enebular.com/samples/use-airtable-as-spreadsheet2/)

の仕組みを活用しています。

1 件ごとに分解して即座に Airtable に書き込むので Airtable の API 書き込み限界を越える心配があるものの、15 分ごとの取得であれば、多くて 5 件くらいなので、今回はこうしています。

では、設定をはじめていきましょう。

## Twitter の BearerToken を設定

![image](https://i.gyazo.com/c1711a6f6d227e6f48ba3473fda5cad6.png)

こちらの TwitterBearerToken と書かれた change ノードをダブルクリックしてプロパティ画面を表示します。

![image](https://i.gyazo.com/a8cca154c8c663a2de2477aabc69de9e.png)

`<BearerToken>` を自分の Twitter 開発者アカウントで作成した BearerToken に変更します。

## Airtable の API Key を設定

![image](https://i.gyazo.com/ee7df5ca479f78befe98ce10da4fbe37.png)

こちらの airtable と書かれた airtable ノードをダブルクリックしてプロパティ画面を表示します。

![image](https://i.gyazo.com/4ccaac89df3e7bdc62afddddbd7ef3ec.png)

airtable out ノードを編集のプロパティ画面を確認します。テーブル名は、このまま `Table 1` を使うのでそのままでOKです。

Set API Key の項目で My API Key が選択されているのを確認し、横の鉛筆ボタンをクリックして編集します。

![image](https://i.gyazo.com/81b4755f7387ce92f5fd93b559eba7de.png)

airtable ノードのプロパティ編集画面に移動します。

- API Key
  - 今回用意した自分のアカウントの API Key
- Base Id
  - さきほど作成した Airtable Base のメモした Base ID

を入力します。更新ボタンをクリックして設定を更新し、airtable out ノードを編集のプロパティ画面に戻ります。

![image](https://i.gyazo.com/39fd954bcac5f7d91cde1437c6e382a3.png)

完了ボタンをクリックして設定を完了します。

![image](https://i.gyazo.com/76b35427f8d376bcb1208d1bd69e2eb8.png)

デプロイボタンをクリックして設定を反映します。


これで準備完了です。

## 次は

お疲れ様でした。

左のメニューから次のコンテンツ「フローを試してみよう」をクリックしましょう。