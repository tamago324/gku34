## GPK FWMaker でのビルド方法について

QMK のファームウェアをビルドするために[GPK FWMaker](https://github.com/darakuneko/gpk_fwmaker) が使用できます。
Docker を使用して簡単にビルドできるのでオススメです。

### Docker のインストール

https://www.docker.com/ から環境にあったものをダウンロードし、インストールします。

インストールが完了したらPCの再起動します。

### GPK FWMaker のダウンロード

https://github.com/darakuneko/gpk_fwmaker/archive/refs/heads/main.zip でダウンロードします。

### 初期セットアップ

ダウンロードしたディレクトリに移動し、

```
cd gpk_fwmaker
docker compose build
```

を実行。

### ツールの起動

```
cd gpk_fwmaker
docker compose up -d
```

### QMKのキーボードディレクトリをコピーする

GPKFW ディレクトリに QMKの [keyboards/tamago324/gku34](https://github.com/tamago324/qmk_firmware/tree/tamago324_v2/keyboards/tamago324/gku34) ディレクトリを、環境に合わせて以下のディレクトリにコピーする

windows: `C:\Users\xxxx\GPKFW`
mac: `/Users/xxxx/GPKFW`
ubuntu: `/home/xxxx/GPKFW`

例えば、Windows の場合、`C:\Users\xxxx\GPKFW\gku34` にコピーする

![](assets/1_10.png)

### ファームウェアの作成

以下のコマンドを実行し、ファームウェアを作成する

Windows の場合:

```
# qmk の場合
curl -X POST -H "Content-Type: application/json" -d "{\"kb\": \"gku34/rev01\", \"km\": \"default\", \"tag\": \"0.21.5\"}" 127.0.0.1:3123/build/qmk

# vial の場合
curl -X POST -H "Content-Type: application/json" -d "{\"kb\": \"gku34/rev01\", \"km\": \"vial\"}" 127.0.0.1:3123/build/vial
```

`C:\Users\xxxx\GPKFW` に `gku34_rev01_default.uf2` が生成される

### ファームウェアの書き込み

RP2040-Zero の左側のボタンを押しながら、USB を接続する

新しいデバイスとしてファイルエクスプローラに表示された、キーボードに生成された `gku34_rev01_default.uf2` をコピーします。コピーが完了すると、デバイスが切断されます。

デバイスが切断されたら、ファームウェアの書き込みが完了です。
