# はじめに

## 今回の仕組み

![image](https://i.gyazo.com/cdee80533efcf79980f8d1b0369eacb5.png)

今回の仕組みは enebular editor と Power Automate Desktop が連携する仕組みです。

![image](https://i.gyazo.com/affaa7c18e2cdeb1bf4732270035c8c4.png)

enebular editor が為替情報のAPIである [Exchange Rates API](https://exchangeratesapi.io/) とのやり取りを担当して、Power Automate Desktop が Excel にデータを保存するところを担当します。

![image](https://i.gyazo.com/f6f3e00549fff2e875513bbbbcfc8021.png)

具体的には enebular editor が API との接続と受け取ったデータを使いやすく加工するところを担当します。Power Automate Desktop は enebular editor からデータを受け取って Excel にデータを保存するところを担当します。

## 為替 API の話

![image](https://i.gyazo.com/2fd869e56464e48982ace165f688be45.png)

[Exchange Rates API](https://exchangeratesapi.io/) が提供している色々な通貨の為替情報をフリーで提供してくれます。

![image](https://i.gyazo.com/1a2442b8bdbfecfad8e8ad424e11952f.png)

ユーロの為替情報を表示する API の例。

https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies/eur.json 

## ではさっそく

左のメニューから次のコンテンツ「enebular editor でフローを呼び出そう」をクリックしましょう。