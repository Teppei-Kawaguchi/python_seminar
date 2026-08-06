# Lesson 1: Python実行環境

Pythonセミナーの導入回です。Python 3.11、uvによるlesson単位の仮想環境、サーバ接続、Git/GitHubを使った教材管理の基礎を扱います。

## 主なファイル

- `第１回Pythonセミナー_資料.pptx`: 導入用資料
- `第1回pythonセミナー.pptx`: 別版の第1回資料
- `pyproject.toml` / `uv.lock`: 最小のNotebook kernel環境
- `main.py`: uv初期化時の表示用雛形

このlessonには演習NotebookやCSVはありません。授業内容の正本を判断するときは、ファイル名だけで版を統合せず、ユーザーが指定したPPTXを使ってください。

## 実行環境

```bash
uv lock --check
uv sync --frozen
uv run python main.py
```

最後のコマンドは環境確認用で、教材本体の実行ではありません。共通ルールは [../README.md](../README.md) を参照してください。
