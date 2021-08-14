# 結果

　[SA-46][]を手で演奏し、その結果を耳でリアルタイムに聞きつつ、[ラズパイ4][]で録音できた。

* [demo](https://ytyaru.github.io/Shell.Casio.SA46.Record.20210814131806/)

# 手順

## 必要なもの

* [SA-46][]
* [ラズパイ4][]
* [UGREEN 30724 USBサウンドカード][]
* [KA333 ステレオケーブル（抵抗入り）][]

[SA-46]:https://www.amazon.co.jp/gp/product/B003KZBFIS/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1
[ラズパイ4]:https://www.amazon.co.jp/gp/product/B095K5WTQ2/ref=ppx_yo_dt_b_asin_title_o07_s00?ie=UTF8&psc=1
[UGREEN 30724 USBサウンドカード]:https://www.amazon.co.jp/gp/product/B01N41607I/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1
[KA333 ステレオケーブル（抵抗入り）]:https://www.amazon.co.jp/gp/product/B000227SS8/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1

## 接続

```
ラズパイ4
｜
USB2.0
｜
サウンドカード
｜
Mic | Speaker
｜    ｜
SA-46 イヤホン
｜    ｜
手    耳
```

## インストール

　録音したりノイズ除去したりするソフトウェアを入れる。

```sh
sudo apt install -y audacity
```

## 入出力設定

　接続できたら入出力設定する。

機器|設定
----|----
SA-46|電源プラグを挿す。電源`入`スイッチをONにする。
ラズパイ|タスクバー右上の`🔊`アイコンを右クリックして`Audio Outputs`と`Audio Inputs`をそれぞれ希望のものにする。今回はどちらも`USB Audio Device`にした。
ラズパイ|`Audacity`を起動する。録音`🎤`と再生`🔊`のデバイスを上記で設定したのと同じものにする。今回は`USB Audio Device - hw:2,0`にした。
ラズパイ|`Audacity`のメニュー→`Transport`→`Transport Options`にある`Overdub`と→`Software PlayThrouth`にチェック`✔`を入れる。
ラズパイ|`Audacity`の録音ボタン`●`を押す
SA-46|キーボードを押すと音がイヤホンから聞こえるはず。録音もできているはず。

# 参考

* [録音の雑音を消す-Audacity｜Linuxと歩む - FC2](http://linux10.blog.fc2.com/blog-entry-4.html)
* [Raspberry Pi で再生と録音を行う](https://blog.natade.net/2019/08/27/raspberry-pi-%E5%86%8D%E7%94%9F-%E9%8C%B2%E9%9F%B3-%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9/)
* [unable to overdub](https://forum.audacityteam.org/viewtopic.php?t=100631)
