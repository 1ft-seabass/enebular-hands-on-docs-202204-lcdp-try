![image](https://i.gyazo.com/cbc1f6e4afa35f95554d9b116991eb65.png)

# フローを試してみよう

これで、連携する仕組みが整いました。

WEB エディタで実際に実行してみましょう。

## WEB エディタで実際に実行してみましょう

![image](https://i.gyazo.com/7525befb84b02360559d8da2fe233121.png)

まず、動作確認をしてます。WEB エディタでフローを開きましょう。

![image](https://i.gyazo.com/ed794fa846c36cd41de57e46c3e86247.png)

テスト用タイムスタンプという名前の inject ノードでテストしてみましょう。

![image](https://i.gyazo.com/a5a225cc82283cb7baafc1bf1fd00fb6.png)

ボタンをクリックして動かします。

![image](https://i.gyazo.com/7816d55ed5175bef63a7ae4406c03d66.png)

![image](https://i.gyazo.com/8e811d0ae2f2b3ff9274e3e7452f32c7.png)

すると、ツイート取得後のこちらの debug ノードに結果が返ってきます。

![image](https://i.gyazo.com/678787565dfe137153987b67170031dc.png)

`{ data: array[2] ～～` と書かれたところがツイート取得された結果です。今回のフローは 15 分間で取得するようにできているので、クリックしたときから、さかのぼって 15 分間でツイートがあれば取得結果が見れます。

![image](https://i.gyazo.com/a80d8ccbaaf4ad99966a7edd59687b86.png)

JSON のツリーを開いて今回の内容を見てみます。無事取得されていました。

## Airtable の記録も確認してみる

![image](https://i.gyazo.com/ef2c89a033d83d501c99f8153d006447.png)

Airtable への記録の結果はこちらの debug ノードで確認できます。

![image](https://i.gyazo.com/0e7efa4a25f9defdfeadebe37665dfe4.png)

今回の記録されたデータの結果が返ってきます。この id というのは Airtable で保存された行です。

![image](https://i.gyazo.com/12562ce6f8d90a963964e43f385677a6.png)

Airtable で確認してみたところ、無事記録されていました。（明るめの話題が出る時期を厳選してキャプチャしました！）

## 次は

お疲れ様でした。

左のメニューから「実行環境の設定をして動かしてみる」をクリックしましょう。