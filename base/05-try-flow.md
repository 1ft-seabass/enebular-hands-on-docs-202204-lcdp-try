![image](https://i.gyazo.com/cbc1f6e4afa35f95554d9b116991eb65.png)

# いよいよ動かしてみよう

これで、enebular editor と Power Automate Desktop が連携する仕組みが整いました。

あともう少しです。

## enebular editor を起動したままか確認

![image](https://i.gyazo.com/35c38ff126f672e70060dd47256b1016.png)

何かの拍子に閉じてるかもしれないので enebular editor を起動したままか確認します。

## enebular editor の動作を確認する

Power Automate Desktop の実行先の、enebular editor のデータの入口（HTTP in）をブラウザで確認しましょう。

`http://localhost:1888/api`

こちらのアドレスを

![image](https://i.gyazo.com/4bdaf72650c8da7c47ae93906eccb74b.png)

Chrome ブラウザのアドレス欄に入力して、アクセスしてみましょう。

![image](https://i.gyazo.com/dc991970f05e654f2f68fbcb426315f9.png)

このように、アクセスできデータが取得出来たら、enebular editor の動作確認は完了です。

## Power Automate Desktop の実行速度を変更する

![image](https://i.gyazo.com/a8a59a7dcd13f6b3b7dfd5897565dd77.png)

Power Automate Desktop は、1つ1つのアクションを実行するときに時間間隔を設定しています。

下部に設定があります。

![image](https://i.gyazo.com/4ddef759c632479e4ab04413d52fc613.png)

デフォルトでは、100 ミリ秒です。

![image](https://i.gyazo.com/f8c345422db7310803dbfe81cbcef121.png)

このまま実行してしまうと、終わるまでに結構時間がかかるので、1ミリ秒にします。

## 実際に実行してみましょう

![image](https://i.gyazo.com/de9fb442046439749482f400ed59f8d3.png)

実行ボタンをクリックしてみましょう。

![image](https://i.gyazo.com/cdee80533efcf79980f8d1b0369eacb5.png)

enebular editor につながると実際の為替 API にデータを取得してきて Power Automate Desktop が Excel にデータを保存し始めます。

![image](https://i.gyazo.com/54e281f698fd9b7926a059b16620022c.png)

しばらく待っていると Excel に書き込まれます。

![image](https://i.gyazo.com/533b1992dea4348bd700aa680c694b26.png)

なお、この時点では sample.xlsx は保存されていないので、自分で保存しましょう。

## ふりかえり

![image](https://i.gyazo.com/ba61f6f0d0e3915455db3ec73508e467.png)

Node-RED と Power Automate Desktop でバランスよく自動化を作ってみました。

![image](https://i.gyazo.com/78ee8a3ed0edc1a202661621edc6230e.png)

Power Automate Desktop はデスクトップの自動化に関しては多彩です。Excel の読み書き、ダイアログや音を出したり Node-RED では手間がかかることが手軽にできます。

![image](https://i.gyazo.com/f831be9532fa2a8157bc601c52a60e38.png)

Node-RED はいろいろな API へつなぎやすくその後のデータ加工が得意です。Power Automate Desktop では手間が多くなる部分がやりやすいです。

![image](https://i.gyazo.com/992a746d879e34375f197313a3c8a986.png)

Node-RED でデータ加工をうまくやり Power Automate Desktop がデータ保存を担うやりかたで、取得したい API が変わっても対応しやすそうです。

もちろん1ツールに寄せるのもアリだと思うし、こういう連携でやりたいことを探っていくことができるのは面白いところです。

請求書を経理データから自動入力作成とか作業報告書とか予定表とかを自動で入れるとか、Excel 入力も色々できることがありそうなので、ぜひこの仕組みで色々試してみてください！

Node-RED と Power Automate Desktop でよき業務自動化ライフを！


## 次は

お疲れ様でした。

左のメニューから「Introduction」をクリックして戻りましょう。