# study-quantum

書籍「いちばんやさしい量子コンピューターの教本」の読み進め練習用リポジトリ。

## 環境セットアップ

### テスト環境

- Windows 11
- Miniconda 4.12.0

### Miniconda のインストール

Miniconda3 Windows版をインストール。

https://docs.conda.io/en/latest/miniconda.html

(※注) インストーラーを使うこと。Scoop経由のインストールでは pip が SSLエラーを出してうまくいかない

### 環境作成

「Anaconda Powershell Prompt (miniconda3)」を開く。

以下の (A) (B) いずれかの手順でパッケージをインストールなどをする。

(※注) 必ず Anaconda Prompt を使うこと。通常の PowerShell では conda activate コマンドがうまくいかない

#### (A) enviroment.yml で作業環境を作成

enviroment.yml の内容に従って作業用の環境「env-blueqat」「env-wildqat」を作成する:

```shell
$ conda create -f env-blueqat.yml
$ conda create -f env-wildqat.yml
```

Blueqatを使用する場合は env-blueqat 環境に入る:

```shell
$ conda activate env-blueqat
```

Wildqatを使用する場合は env-wildqat 環境に入る:

```shell
$ conda activate env-wildqat
```

#### (B) いちから作業環境を作成

condaコマンドで作業用の環境「env-blueqat」「env-wildqat」を作成する。

```shell
$ conda create -n env-blueqat python=3.9
$ conda create -n env-wildqat python=3.7
```

env-blueqat 環境に入り、Pythonバージョンが 3.9 になっていることを確認。

```shell
$ conda activate env-blueqat
(env-blueqat) $ python --version
Python 3.9.12
```

量子計算SDK「Blueqat」と「Jupyter Lab」をインストール:

```shell
(env-blueqat) $ pip install blueqat jupyterlab
```

enviroment.yml を出力:

```shell
(env-blueqat) $ conda env export > env-blueqat.yml
```

env-wildqat 環境に入り、Pythonバージョンが 3.7 になっていることを確認。

```shell
$ conda activate env-wildqat
(env-wildqat) $ python --version
Python 3.7.13
```

量子アニーリングSDK「Wildqat」と「Jupyter Lab」をインストール:

```shell
(env-wildqat) $ pip install wildqat jupyterlab
```

enviroment.yml を出力:

```shell
(env-wildqat) $ conda env export > env-wildqat.yml
```

## JupyterLab の起動

Blueqat のプログラムを実行する場合は、下記を実行。

```shell
$ conda activate env-blueqat
(env-blueqat) $ jupyter lab
```

Wildqat のプログラムを実行する場合は、下記を実行。

```shell
$ conda activate env-wildqat
(env-wildqat) $ jupyter lab
```

ブラウザで Jupyter Lab が起動する。Jupyterサーバーを終了するには Ctrl + C キーを押す。
