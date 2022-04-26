![image](https://i.gyazo.com/cbc1f6e4afa35f95554d9b116991eb65.png)

# 実行環境の設定をして動かしてみる

さて、これで実行環境で動かすフローの動作確認ができました。

## 実行環境へ移動

![image](https://i.gyazo.com/c3e5ac65145b997d08e27837f8b74d8d.png)

WEB エディタを閉じてフロー概要に戻ります。

![image](https://i.gyazo.com/f810fb9463c847a927f139029626d7b8.png)

こちらのプロジェクト名をクリックしてプロジェクト画面に戻ります。

![image](https://i.gyazo.com/136e5bdf2207551e2b8f48faeddd1743.png)

メニューから実行環境をクリックして、実行環境の設定に移動します。

## 実行環境の作成とデプロイ

[新リリースのenebularクラウド実行環境の使い方 | enebular blog](https://blog.enebular.com/enebular/how-to-use-enebular-cloud-exec-environment/)

こちらを参考に進めていきます。

![image](https://i.gyazo.com/8f7200f48bdaf7bb4c7ac3cc9c3ffef8.png)

右下の＋ボタンをクリックして、

![image](https://i.gyazo.com/699dc4ce61dfdf5ffd28347fb7e9fa33.png)

実行環境の名前を決めて OK ボタンをクリックします。

![image](https://i.gyazo.com/2076210357c23eb2359649944e8975cc.png)

作成を待ちます。

![image](https://i.gyazo.com/894dd135563ef385e0b6c3b3e67b0000.png)

設定が出来上がりました。

![image](https://i.gyazo.com/b872fdb74334be36fb48794af8fabec0.png)

デプロイボタンをクリックします。

![image](https://i.gyazo.com/5cc42ea0f6c5eb7b74b9b850bf747c18.png)

デプロイするフローを選択する画面になるので、今回のフローを選択してデプロイをクリックします。

![image](https://i.gyazo.com/e0122d8011e4dc9477942f021e9d9b63.png)

デプロイ履歴の画面になり、デプロイ中となります。

![image](https://i.gyazo.com/6b111b268581ef082996cf19c6dbd263.png)

デプロイステータスがデプロイ済みになるまで待ちましょう。

## 実行環境の設定

![image](https://i.gyazo.com/471e0829ba0c73c0980ca0de8054d40f.png)

デプロイのメニューから設定をクリックします。

![image](https://i.gyazo.com/d50f5511bd1d62cd023103eae897821e.png)

実行環境の設定画面に移動しました。

![image](https://i.gyazo.com/2176ad698f195d3c0d9f88e23ab96b94.png)

「設定を編集する」をクリックします。

![image](https://i.gyazo.com/0a99290788e464cc3befd76d5af991b1.png)

スケジュールトリガーに移動します。

![image](https://i.gyazo.com/ecb81042a5c5750dc3220529ac111e92.png)

スイッチをクリックして ON にします。

![image](https://i.gyazo.com/33855577f5c271943a8720b397032c7a.png)

毎時に設定します。

![image](https://i.gyazo.com/3e22cc16a8763991a85668ce54ea5b7e.png)

0 と 15 を選択します。

![image](https://i.gyazo.com/315b53e2afdad79595208e6961124a82.png)

30 と 45 を選択します。

![image](https://i.gyazo.com/d91eb917132b62aecf601b18d9d1842b.png)

15 分ごとの実行である `毎 15` に設定されていることを確認します。

![image](https://i.gyazo.com/5a77e6138a61d72de0a7326119b0db6c.png)

保存ボタンをクリックして実行環境の設定を完了します！

## 15 分ほど次の実行を待ってログを見てみる

![image](https://i.gyazo.com/7816d55ed5175bef63a7ae4406c03d66.png)

![image](https://i.gyazo.com/32187ede9b8bde7a63e13063039441ed.png)

今回のフローは各 debug ノードでシステムコンソールにログを出力しているので、実行環境のログから動作を確認できます。

![image](https://i.gyazo.com/d14542612f3e69682f7486e16ff26443.png)

実行環境のメニューからログをクリックします。

![image](https://i.gyazo.com/5dd0ac4382c576227c5bfae4f2295ff1.png)

実行直後はログがありませんが、15分ごと経過するとログが出力されるはずです。

## 次は

お疲れ様でした。

左のメニューから「Introduction」をクリックして戻りましょう。