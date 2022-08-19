# study-quantum

書籍「いちばんやさしい量子コンピューターの教本」の読み進め練習用リポジトリ。

## 環境セットアップ

### テスト環境

- Windows 11
- PowerShell 7.2.6
- Python 3.10.6

### Pythonのインストール

まずScoopをインストールし、ScoopでPythonをインストール。

```shell
$ Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
$ scoop install python
```

インストール済みの場合は Pythonとpipなどを最新にアップデートしておく。

```shell
$ scoop update python
$ pip install --upgrade pip setuptools wheel
```

### Python仮想環境(venv)の作成

このリポジトリのルート作業ディレクトリで venv を作成:

```shell
$ cd study-quantum
$ python -m venv .venv
```

### パッケージのインストール

venv 環境に入る:

```shell
$ .\.venv\Scripts\activate
```

以下の (A) (B) いずれかの手順でパッケージをインストールする。

#### (A) requirements.txt の内容を元にパッケージをインストール

requirements.txt の内容に従って pipパッケージをインストール:

```shell
(.venv) $ pip install -r requirements.txt
```

#### (B) pipコマンドでパッケージをインストール

venv 環境上に Jupyter Lab と量子計算SDK「Blueqat 1.x」をインストール:

```shell
(.venv) $ pip install jupyterlab
(.venv) $ pip install blueqat==1.*
```

requirements.txt を出力:

```shell
(.venv) $ pip freeze > requirements.txt
```

#### venv終了

最後に venv 環境から出る:

```shell
(.venv) $ deactivate
```

## JupyterLab の起動

venv 環境で下記を実行。

```shell
(.venv) $ jupyter lab --no-browser
```

表示されたURLを Control + クリックして、ブラウザで開く (※コンソール端末が Windows Terminal の場合)。

終了するには、Ctrl + C キーを押す。
