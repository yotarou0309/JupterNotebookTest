# VS CodeとDockerを使って、Jupyter Notebook環境を構築する

PythonのDockerイメージ作成に関しては、以下を参考にさせていただきました。

[Python3をDockerでrequirements.txtを使用した環境構築](https://note.com/hiropython/n/n83554165d43c)

手順は以下

- WSL2のインストール(やらなくてもよい)
- Docker Desktop for Windowsのインストール
- VSCodeのインストール
- VSCodeでJupyter Notebookを開く

## WSL2のインストール(やらなくてもよい)

極力自分のPCを汚したくないという理由で利用。それ以外の理由では特に必要ない。

## Docker Desktop for Windowsのインストール

[インストールを行う](https://docs.docker.jp/docker-for-windows/install.html)

## VSCodeのインストール

[インストールを行う](https://www.javadrive.jp/vscode/install/index1.html)

## VSCodeでJupyter Notebookを開く

適当な場所にフォルダを作成し、その中に本リポジトリの

- Dockerfile
- requirements.txt

の2ファイルを配置する。

その後、このフォルダをVS Codeで開く。その後の手順は以下。

1. VS Codeの左下の緑("><"のようなマーク)の部分をクリックする
2. コマンドパレットが開くので、「Reopen in Container」をクリックする
3. Dockerコンテナが開くまで少し待つ
4. .ipynbファイルを作成する(ex mynotebook.ipynbなど)
5. .ipynbファイルを追加するとVS Codeが自動的にその拡張子に対応したJupyter Notebook用のプラグインを読み込んでくれる

## Python環境のカスタマイズ

requirements.txtの内容を変更することで、必要なライブラリを取り込むことように調整できます。今回の環境構築では、データ分析の前処理の**勉強**に使うことを想定したものになっています。

必要に応じて、ライブラリを追加・削除したり、バージョンを指定することができ、明示的に**管理**することができるのがこの方法のメリットだと思います。

Dockerイメージを再構築したい場合は、コマンドパレットから、`Rebuild Container`をすると、再構築できます。
