# はじめに

## 今回の仕組み

![image](https://i.gyazo.com/1b7eb455504d7f3c61510e8855a27c63.png)

今回の仕組みは enebular の実行環境を使って Twitter からのツイート取得と、そのデータを AirTable に保存する流れを定期的に行います。

![image](https://blog.enebular.com/wp-content/uploads/2022/04/2022_0426_CloudEnv-800x400.png)

## Twitter API v2 によるツイート取得

[Twitter API v2 でのツイート定期取得を enebular 実行環境で試す | enebular blog](https://blog.enebular.com/samples/twitter-api-v2-%E3%81%A7%E3%81%AE%E3%83%84%E3%82%A4%E3%83%BC%E3%83%88%E5%AE%9A%E6%9C%9F%E5%8F%96%E5%BE%97%E3%82%92-enebular-%E5%AE%9F%E8%A1%8C%E7%92%B0%E5%A2%83%E3%81%A7%E8%A9%A6%E3%81%99/)

前半の Twitter API v2 を実行環境で試す部分は、enebular blog のこちらの記事でもくわしく書かれているので、ご参考ください。

- [Flow EditorからTwitter API v2でツイートを定期取得してみる | enebular blog](https://blog.enebular.com/samples/query-tweets-on-enebular-web-flow-editor/)
- [enebular から Twitter API v2 でツイートを取得してみる | enebular blog](https://blog.enebular.com/samples/query-tweets-with-enebular-via-twitter-apiv2/)

と、少しずつ仕組みをステップアップして今回のツイート取得の仕組みになっています。

## Airtable によるデータ書き込み

![image](https://blog.enebular.com/wp-content/uploads/2021/10/enebular-airtable_01.png)

Airtable によるデータ書き込みについても enebular blog のこちらの記事でもくわしく書かれているので、ご参考ください。

- [スプレッドシートのようにデータ管理できる Airtable を Node-RED ノードでセットアップしてみる | enebular blog](https://blog.enebular.com/samples/use-airtable-as-spreadsheet1/)
- [スプレッドシートのようにデータ管理できる AirtableをNode-REDノードでデータを書き込んでみる | enebular blog](https://blog.enebular.com/samples/use-airtable-as-spreadsheet2/)

今回の仕組みは「Twitter API v2 によるツイート取得」「Airtable によるデータ書き込み」を掛け合わせたものになります。

## enebular の実行環境の話

![image](https://blog.enebular.com/wp-content/uploads/2022/02/apps-menu-800x400.png)

[Web APIが簡単に作れたり、クラウド上での定期実行も可能な実行環境をリリース | enebular blog](https://blog.enebular.com/function/apps-environment/)

enebular の実行環境は最近リリースされました。

実行環境は、Node-REDのフローを実行するクラウド環境です。Node-REDでWeb APIが簡単に作れたり、クラウド上での定期実行もできます。

[新リリースのenebularクラウド実行環境の使い方 | enebular blog](https://blog.enebular.com/enebular/how-to-use-enebular-cloud-exec-environment/)

もちろん、ドキュメントも参考になりますが、この記事が、はじめての方でしたら実行環境の使い方が触れやすいので、今回のハンズオンで気になった方は是非見てみてください。


## ではさっそく

左のメニューから次のコンテンツ「enebular プロジェクトに実行環境を準備しよう」をクリックしましょう。