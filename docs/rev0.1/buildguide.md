# gku34 ビルドガイド

gku34 rev0.1 のビルドガイドです。

<details><summary>目次</summary><div>


* [キットに含まれるもの](#キットに含まれるもの)
* [キット以外に必要なもの](#キット以外に必要なもの)
* [組み立て順序の確認](#組み立て順序の確認)
* [組み立て](#組み立て)
  * [1. プレートの側面をペンで塗る](#1プレートの側面をペンで塗る)
  * [2. RP2040-Zero のボタンをペンで塗る](#2rp2040-zero-のボタンをペンで塗る)
  * [3. ダイオードのはんだ付け](#3-ダイオードのはんだ付け)
  * [4. RP2040-Zero のはんだ付け](#4-rp2040-zero-のはんだ付け)
  * [5. スイッチのはんだ付け](#5-スイッチのはんだ付け)
  * [6. ボトムプレートを取り付ける](#6-ボトムプレートを取り付ける)
  * [7. キーキャップを取り付ける](#7-キーキャップを取り付ける)
  * [8. キーマップを変更する](#8キーマップを変更する)
* [最後に](#最後に)

</div></details>


## キットに含まれるもの

| No. | 名前                  | 数量        | 備考                                                                                                                                                                        |
|-----|-----------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | PCB                   | 1枚         | メインPCB                                                                                                                                                                   |
| 2   | ボトムプレート        | 1枚         | ボトムプレート (ゴムシート付き)                                                                                                                                                      |
| 3   | トッププレート        | 1枚         | 家庭用3DPで印刷したトッププレート<br>                                                                                                                                                      |
| 4   | ダイオード            | 34個 + 予備 | [遊舎工房](https://shop.yushakobo.jp/collections/all-keyboard-parts/products/a0800di-02-100)で購入できます。                                                                |
| 5   | 両面テープ (5mm幅)    | -           | PCBとボトムプレートを張り合わせるために使用。 <br>[Amazon](https://www.amazon.co.jp/gp/product/B00VFSHS1K/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1)で購入できます。 |
| 6   | RP2040-Zero | 1個 | [スイッチサイエンス](https://www.switch-science.com/products/7886/) で購入できます。 |
| 7   | ピンヘッダ | 1個 | RP2040-Zero をまっすぐはんだ付けするために使用するピンヘッダ |

## キット以外に必要なもの

| 名前                     | 数量 | 備考                 |
|--------------------------|------|----------------------|
| キースイッチ             | 34個 | choc v1用のキーキャップ  |
| キーキャップ             | 34個 | choc v1スイッチ         |
| USBケーブル              | 1個  | Type-C の USBケーブル |


## 組み立て順序の確認

1. プレートの側面をペンで塗る
2. RP2040-Zero のボタンをペンで塗る
3. ダイオードのはんだ付け
4. RP2040-Zero のはんだ付け
5. スイッチのはんだ付け
6. ボトムプレートを取り付ける
7. キーキャップを取り付ける
8. ファームウェアの書き込み

## 組み立て


### 1.プレートの側面をペンで塗る

PCB と ボトムプレートの側面を[ポスカ](https://amzn.asia/d/1ZZTGt9)などのペンで塗ります。


### 2.RP2040-Zero のボタンをペンで塗る

RP2040-Zero のボタンを[マッキー](https://amzn.asia/d/gaXAFb8)などのペンで塗ります。

これをすることにより、トッププレートを合わせたときに真っ黒になります。

### 3. ダイオードのはんだ付け

PCBの裏にダイオードを34個はんだ付けします。
「PCBのシルクの線」と「ダイオードの線」が一致するようにはんだ付けします。
はんだごての温度は320℃くらいに設定し作業します。

片側に予備ハンダを行い、
ピンセットを使用して、はんだ付けを行い、
もう片方もはんだ付けします。

すべてのダイオードのはんだ付けが終わったら、すべてのダイオードが同じ向きになっていることを確認してください。

### 4. RP2040-Zero のはんだ付け

「PCB の表面の 5V」が「RP2040-Zero の 5V」にあうように合わせます。

ピンヘッダを3つくらいに分け、RP2040-Zero と PCB に刺して、まっすぐなるように合わせます。

RP2040-Zero の角を4箇所はんだ付けをし、浮いていないことを確認してから、すべてをはんだ付けします。

### 5. スイッチのはんだ付け

トッププレートとPCBを合わせて、PCBの表からスイッチを差し込み、裏からスイッチをはんだ付けします。
はんだごての温度は320℃くらいに設定し作業します。

### 6. ボトムプレートを取り付ける

両面テープをPCBに貼り付け、ボトムプレートがずれないように貼り付けます。

### 7. キーキャップを取り付ける

キーキャップを取り付けます。

### 8.キーマップを変更する

Remap か QMK を使用してキーマップを変更可能です。

* Remap の場合: キーボードカタログの gku34 のページで設定可能です。
* QMK の場合: [tamago324/qmk_firmware](https://github.com/tamago324/qmk_firmware/tree/tamago324/keyboards/tamago324/gku34) の `tamago324` ブランチの `keyboards/tamago324/gku34` にファームウェアがあります。また、バージョンは 0.18系です

<details><summary>[GPK FWMaker](https://github.com/darakuneko/gpk_fwmaker)で書き込む場合</summary><div>

QMK のファームウェアをビルドするために[GPK FWMaker](https://github.com/darakuneko/gpk_fwmaker) が使用できます。
Docker を使用して簡単にビルドできるのでオススメです。

#### Docker のインストール

https://www.docker.com/ から環境にあったものをダウンロードし、インストールします。

インストールが完了したらPCの再起動します。

#### GPK FWMaker のダウンロード

https://github.com/darakuneko/gpk_fwmaker/archive/refs/heads/main.zip でダウンロードします。

#### 初期セットアップ

ダウンロードしたディレクトリに移動し、

```
cd gpk_fwmaker
docker compose build
```

を実行。

#### ツールの起動

```
cd gpk_fwmaker
docker compose up -d
```

#### QMKのキーボードディレクトリをコピーする

GPKFW ディレクトリに QMKの keyboards/tamago324/gku34 ディレクトリを、環境に合わせて以下のディレクトリにコピーする

windows: `C:\Users\xxxx\GPKFW`
mac: `/Users/xxxx/GPKFW`
ubuntu: `/home/xxxx/GPKFW`

例えば、Windows の場合、`C:\Users\xxxx\GPKFW\gku34` にコピーする

![](assets/1_10.png)

#### ファームウェアの作成

以下のコマンドを実行し、ファームウェアを作成する

Windows の場合:

```
curl -X POST -H "Content-Type: application/json" -d "{\"kb\": \"gku34/rev01\", \"km\": \"default\", \"tag\": \"0.18.17\"}" 127.0.0.1:3123/build/qmk
```

`C:\Users\xxxx\GPKFW` に `gku34_rev01_default.uf2` が生成される

#### ファームウェアの書き込み

RP2040-Zero の左側のボタンを押しながら、USB を接続する

新しいデバイスとしてファイルエクスプローラに表示された、キーボードに生成された `gku34_rev01_default.uf2` をコピーします。コピーが完了すると、デバイスが切断されます。

デバイスが切断されたら、ファームウェアの書き込みが完了です。

</div></details>


## 最後に

完成したキーボードの写真を SNS に投稿していただけるととても嬉しいです！

(ハッシュタグは `#gku34` です。)

