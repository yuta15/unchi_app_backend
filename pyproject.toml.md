
[project]
// プロジェクト全体の設定
name = "unchi-app-backend"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
// Python versionの指定
requires-python = ">=3.12"
// 本番環境向け依存関係
dependencies = []

[dependency-groups]
// 開発環境でのみ必要な依存関係
dev = [
    "mypy>=1.18.2",
    "pytest>=9.0.1",
    "ruff>=0.14.6",
]

[tool.ruff]
exclude = [
    ".bzr",
    ".direnv",
    ".eggs",
    ".git",
    ".git-rewrite",
    ".hg",
    ".ipynb_checkpoints",
    ".mypy_cache",
    ".nox",
    ".pants.d",
    ".pyenv",
    ".pytest_cache",
    ".pytype",
    ".ruff_cache",
    ".svn",
    ".tox",
    ".venv",
    ".vscode",
    "__pypackages__",
    "_build",
    "buck-out",
    "build",
    "dist",
    "node_modules",
    "site-packages",
    "venv",
]
line-length = 120
indent-width = 4
target-version = "py312

[tool.ruff.lint]
// ルールコード
| プレフィックス / コード | 元ツール / プラグイン      | 主なチェック内容                                      | 代表的なルール例                                     |
|-------------------------|----------------------------|------------------------------------------------------|------------------------------------------------------|
| F                       | Pyflakes                   | 未使用変数・未使用インポート・未定義名などのバグ系   | F401: unused import（未使用インポート）             |
| E, W                    | pycodestyle                | PEP8 ベースの構文＆スタイル（行長・インデントなど） | E501: line too long（行が長すぎる）                 |
| I                       | isort                      | import 文のソート＆グルーピング                      | I001: unsorted-imports（未ソートのインポート）      |
| B                       | flake8-bugbear             | バグの温床になりやすいコードパターン                 | B006: mutable default argument                       |
| S                       | flake8-bandit              | セキュリティ関連（危険な関数・暗号など）             | S101: use of assert（assert の使用）                |
| D                       | pydocstyle                 | Docstring の有無・形式                               | D100: missing docstring in public module            |
| N                       | pep8-naming                | 関数・クラス・変数名の命名規約                       | N802: function name should be lowercase             |
| ANN                     | flake8-annotations         | 型ヒント（type annotation）の有無・漏れ             | ANN001: missing type for function argument          |
| PL                      | Pylint                     | 複雑度や冗長な構造などコード品質全般                 | PLR0915: too many statements                        |
| UP                      | pyupgrade                  | 古い構文を最新の Python スタイルへ改善               | UP032: use f-string instead of format               |
| SIM                     | flake8-simplify            | if / isinstance などの書き方簡略化                   | SIM101: duplicate-isinstance-call                   |
| ARG                     | flake8-unused-arguments    | 未使用の関数・メソッド引数                           | ARG001: unused-function-argument                    |
| Q                       | flake8-quotes              | 文字列や Docstring のクォートスタイル統一           | Q000: bad-quotes-inline-string                      |
| ERA                     | eradicate                  | コメントアウトされた「死んだコード」の検出           | ERA001: commented-out-code                          |
| ISC                     | flake8-implicit-str-concat | 暗黙の文字列連結（隣接リテラルなど）の検出           | ISC001: implicit string concatenation on one line   |
| C4                      | flake8-comprehensions      | 内包表記・ジェネレータ式の改善提案                   | C401: unnecessary-generator-set                     |
| C90                     | mccabe                     | 循環的複雑度（cyclomatic complexity）                | C901: complex structure                             |
| PD                      | pandas-vet                 | pandas のアンチパターン                              | PD002: inplace=True should be avoided               |
| NPY                     | NumPy-specific rules       | NumPy の非推奨 API やアンチパターン                  | NPY002: legacy np.random usage                      |
| PT                      | flake8-pytest-style        | pytest のベストプラクティス                          | PT001: incorrect fixture parentheses style          |
| PTH                     | flake8-use-pathlib         | os.path / os.* を pathlib に置き換え                 | PTH100: os.path.abspath → Path.resolve 推奨         |
| RUF                     | Ruff-specific              | Ruff 独自（noqa 管理などのユーティリティ）          | RUF100: unused-noqa（不要な noqa の検出）          |


select = ["E", "F", "B", "I", "UP", "C4"]
ignore = ["E501"]

[tool.mypy]
// mypyの設定
python_version = "3.12"
strict = true
show_error_codes = true
// mypyの対象外とするファイルを指定する。
// 開発効率に応じて適宜増やす。
exclude = [
    "(^build/|^dist/)",
]