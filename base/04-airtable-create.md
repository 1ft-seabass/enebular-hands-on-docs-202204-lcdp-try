# Airtable にデータを記録する場所を作ろう

![image](https://i.gyazo.com/2fa709857524e4f85423675808a883d4.png)

[スプレッドシートのようにデータ管理できる Airtable を Node-RED ノードでセットアップしてみる | enebular blog](https://blog.enebular.com/samples/use-airtable-as-spreadsheet1/)

こちらの記事をベースに、Airtable についての簡単な紹介と、アカウントの作り方を説明します。

## データのかたまり Base を準備する

AirTable ではスプレッドシートのようなデータのかたまりを Base と呼びます。

![image](https://i.gyazo.com/7f3c881b9b39e492d78012c24ec53669.png)

自分のアカウントの画面から Add a base のボタンからはじめます。

![image](https://i.gyazo.com/1893a73f20c66ef27536fa718b888dd1.png)

Untitled Base ができます。

![image](https://i.gyazo.com/52b501b584f9e18c655b10e7a067c21a.png)

Table 1 を見ます。Name ・ Notes ・ Attachments ・ Status という列ができています。

これを今回のフローで書き出すデータに合わせて修正します。今回はとてもシンプルにします。

- Name
  - 名前を Id に変更
- Notes
  - 名前を Text に変更
- Attachments
  - 削除
- Status
  - 削除
- CreateAt
  - ＋ボタンから新しく

### Status の削除

![image](https://i.gyazo.com/86243a5a2d305cf2d9b946fe27ab610f.png)

まず Status は削除します。

### Attachments の削除

![image](https://i.gyazo.com/434177f93cebaebc8e9fa8b806c0c47d.png)

つづいて Attachments も削除します。

### Name の名前変更

![image](https://i.gyazo.com/10a64d86437992b88a9eb8fd74113897.png)

Name の欄から Customize field type をクリックします。

![image](https://i.gyazo.com/41fcce943accc6e89a69b739c3ad5713.png)

こちらの画面で Name を Id に変更します。

![image](https://i.gyazo.com/28110ec432edaad49f22bb09dfe8d8bc.png)

Id に変更したら Save をクリックします。

### Notes の名前変更

![image](https://i.gyazo.com/298e5ce2a7c1d3b4812b27dfbbd621ce.png)

同じように Notes を Text に変更して Save をクリックします。

### CreateAt の新規作成

![image](https://i.gyazo.com/77d807255dae3d09fecaaa6341fe97e9.png)

Id の項目の横にある＋ボタンをクリックして新しい項目を作成します。

![image](https://i.gyazo.com/1c5e66d7f0ecefd5bd56a9a6861944d0.png)

名前を CreateAt として、タイプを Single line text でクリックします。

![image](https://i.gyazo.com/dd69fb2999cd34f622db4a71e6a38e4c.png)

設定内容を確認して Create fields をクリックします。

![image](https://i.gyazo.com/be1d141e96ee94fa3758a8cd4261167a.png)

これで作成は完了です。

## 初期データの削除

3 行ほど空データがあるので削除しておきます。

![image](https://i.gyazo.com/54bfd73331a096a675965c84264b6d8d.png)

各行の横にチェックボックスがあるのでクリックして選択します。

![image](https://i.gyazo.com/00017537212c7616d9125898c456b01d.png)

3 行選択できたら、

![image](https://i.gyazo.com/d70992f5e9caa45be0e03c0e5bb5ac13.png)

右クリックをして Delete all select records をクリックします。

![image](https://i.gyazo.com/9c7f4902745d7291a88d1fb96018b9bb.png)

無事削除できました。

## 今回作った Base の ID を取得する

![image](https://i.gyazo.com/c2b89f06e739cbaca7e70798e0f5bd81.png)

アカウントでログインした状態で REST API という各 Base の API 取得方法が見られるページに移動します。

- REST API
  - https://airtable.com/api

移動して、

![image](https://i.gyazo.com/50cf4b66015ab442ea780409d0d9aea8.png)

今回作った Base をクリックします。

![image](https://i.gyazo.com/67693477015171884e636cf91d9404dd.png)

INTRODUCTION が表示されるので The ID of this base is のところの app ではじまる Base ID をメモしておきます。

## 次は

お疲れ様でした。

左のメニューから次のコンテンツ「いよいよ動かしてみよう」をクリックしましょう。