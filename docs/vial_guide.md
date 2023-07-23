## Vial を使ったキーマップの変更について

### Vial のインストール

https://get.vial.today/download/ にアクセスし、環境にあったインストーラーをダウンロードし、インストールする

### Vial 用のファームウェアの書き込み

[こちら](../firmware/vial/gku34_rev01_vial.uf2) のファイルをダウンロードします。

RP2040-Zero の左側のボタンを押しながら、USB を接続します。

新しいデバイスとしてファイルエクスプローラに表示されたデバイスにダウンロードしたファイルをコピーします。コピーが完了すると、デバイスが切断されます。

デバイスが切断されたら、ファームウェアの書き込みが完了です。

### Vial の起動、読み込み

Vial を起動します。

gku34 の読み込みがされていない場合、`Refresh` ボタンをクリックします。

`MANUFACTURER gku34` と表示され、gku34 のキーマップが表示されていれば、読み込み完了です。

キーマップの変更が可能です。


### おすすめの設定

少ないキーのキーボードを使用する際に、設定しておきたい項目について説明します。

`QMK Settings > Tap-Hold` タブの項目を設定すると単体押し、長押しの感覚などの設定ができるので、おすすめです。

* `Tapping Term`: 140 など、使いやすい数値に変更します
  * 長押しとして判定するまでの時間です
* `Ignore Mod Tap Interput`: ON にします
  * Mod Tap Key と通常キーを連続して拘束に押したときに両方のキーを Tap として扱う
* `Tapping Force Hold`: ON にします
  * 例えば、`LSFT_T(KC_SPACE)` としていたときに、 `Space` 単体押し直後に `Space` 長押し としたときに、`Space` が連続で入力されてしまう問題が改善されます。

#### 参考文献

* [Ergodox(qmk firmware)の同時押し/レイヤー切替の設定メモ](https://qiita.com/uodna/items/6d23581d26c1adb23377)
* [QMKの「タップ」と「ホールド」を極める - golden-luckyの日記](https://golden-lucky.hatenablog.com/entry/2021/03/06/182958)
* [タップホールド設定](https://docs.qmk.fm/#/ja/tap_hold?id=%e3%82%bf%e3%83%83%e3%83%97%e3%83%9b%e3%83%bc%e3%83%ab%e3%83%89%e8%a8%ad%e5%ae%9a%e3%82%aa%e3%83%97%e3%82%b7%e3%83%a7%e3%83%b3)