# unchi_app_backend

# Settings

|Setting            |Docs                                                       |
|:-----------------:|:----------------------------------------------------------|
|python-version     |3.12                                                       |
|Ubuntu             |22.04                                                      |

## Environment Arguments

|Args               |Docs                                                       |
|:------------------|:----------------------------------------------------------|
|Env                |Dev/Prd                                                    |
|Env                |Dev/Prd                                                    |



## 環境設定方法


### uvのインストール

shを使用する場合のインストール方法
`curl -LsSf https://astral.sh/uv/install.sh | sh`
詳細な設定は[こちら](https://docs.astral.sh/uv/getting-started/installation/)
uvコマンドの自動補完を設定は[こちら](https://docs.astral.sh/uv/getting-started/installation/#shell-autocompletion)

- UVの機能
機能の詳細は[こちら](https://docs.astral.sh/uv/getting-started/features/)

### python versionのインストール
`uv python install <python-version>`

### venvの作成
`.venv`の作成と有効化
`uv venv`
`source .venv/bin/activate`

### pyproject.tomlの内容と同期
以下コマンドで設定の同期
`uv sync --group dev`