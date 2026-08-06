# AGENTS.md - Python Seminar

## 適用範囲と優先順位

このファイルは `python_seminar/` 全体に適用する。指示の優先順は、ユーザーの明示指示、作業対象に最も近い `AGENTS.md`、このファイル、上位階層の `AGENTS.md` とする。作業前にルートと対象lessonの `README.md` / `AGENTS.md` を読む。

## リポジトリ規則

- `python_seminar/` は独立したGitリポジトリである。開始時と完了時に `git status --short --branch` を比較する。
- 各lessonはPython 3.11の独立uvプロジェクトである。コマンドは対象lesson内で実行し、別lessonの `.venv` を流用しない。
- 依存関係の変更指示がない限り、`pyproject.toml`、`uv.lock`、`.python-version` を変更しない。手編集でlock fileを合わせない。
- `main.py` はuvの雛形であり、Notebook処理の正本とみなさない。
- PPTXはGit LFS対象である。バイナリの直接比較、一括置換、LFS pointer状態での上書きをしない。
- 既存Notebook、CSV、PPTXの改名、移動、削除、出力消去、メタデータ一括更新は明示指示がある場合だけ行う。

## Notebookと機械学習

- ファイル参照には相対パスと `pathlib.Path` を優先し、新しい絶対パスを追加しない。
- train/test分割後、scaler、特徴量選択、欠損補完、ADしきい値などを学習データだけでfitする。テストデータを調整に使わない。
- `random_state` などのseed、目的変数、分割比、評価指標、単位を明示し、Notebookの途中実行だけで結果を確定しない。
- Notebookとスライドの両方を変更する場合、図、表、数値、用語、モデル名を同期する。スライドだけから解析条件を推測しない。
- 大きなCSVや計算負荷の高いNotebookは、まず行数制限や対象セルで確認し、完全実行の有無を報告する。

## 既存の未追跡成果物

2026-07-10の開始時点で、次はユーザー作成済みの未追跡ファイルである。対象タスクで明示されない限り内容も追跡状態も変更しない。

- `lesson_7/applicability-domain_2026_07_07.pptx`
- `lesson_7/applicability-domain_method-comparison_supplement_2026_07_07.pptx`
- `lesson_7/applicability-domain_model-comparison_supplement_2026_07_07.pptx`
- `lesson_7/applicability_domain_boston (1).ipynb`
- `lesson_7/applicability_domain_boston_method_comparison.ipynb`
- `lesson_7/applicability_domain_boston_model_comparison.ipynb`
- `lesson_8/test_titanic.csv`
- `lesson_8/train_titanic.csv`

## 検証

- 文書のみの変更: リンクと実在ファイルを確認し、`git diff --check` を実行する。
- 環境定義の変更: 対象lessonで `uv lock --check` と `uv sync --frozen` を実行する。
- Python変更: 対象コードを実行し、入力件数、分割、主要指標を確認する。
- Notebook変更: JSONとして読めること、全セルの実行順、エラー出力、主要結果を確認する。
- 最後に既存の未追跡成果物が維持され、依頼外ファイルが変わっていないことを確認する。
