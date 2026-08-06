# Python Seminar

Pythonセミナーの教材、演習Notebook、データ、発表スライドを回ごとに管理するリポジトリです。ルートに共通のPython環境はなく、各 `lesson_N/` が独立したuvプロジェクトです。

## 構成

| ディレクトリ | 主題 | 現在の中心資料 |
| --- | --- | --- |
| `lesson_1/` | Python 3.11と仮想環境 | 導入スライド |
| `lesson_2/` | 機械学習の基本フロー | 回帰演習Notebook |
| `lesson_3/` | 線形回帰・正則化 | Bostonデータの演習Notebook |
| `lesson_4/` | 特徴量設計・SVR | Lasso/SVR演習Notebook |
| `lesson_5/` | クラス分類 | kNN/Random Forest演習Notebook |
| `lesson_6/` | PCA・クラスタリング | 手書き数字画像の演習Notebook |
| `lesson_7/` | Applicability Domain | BostonデータのAD解析Notebook |
| `lesson_8/` | Titanic演習の準備 | 環境雛形とCSV |

詳細、正本候補、既知の制約は各lessonのREADMEを参照してください。

## 基本操作

作業するlessonへ移動して、そのlessonのlock fileを使います。

```bash
cd lesson_N
uv lock --check
uv sync --frozen
```

- Pythonは各 `.python-version` と `pyproject.toml` に従い、現在は3.11です。
- Notebookは対象lessonを作業ディレクトリとして開き、作成された `.venv` のkernelを選びます。
- `main.py` は全lessonでuv初期化時の表示用雛形です。授業の本体ではありません。
- 依存関係を変える場合だけ `uv add` / `uv remove` を使い、`pyproject.toml` と `uv.lock` を同期します。

## Gitと成果物

このディレクトリは独立したGitリポジトリです。作業前後に `git status --short` を確認してください。

PowerPointは `.gitattributes` によりGit LFSで管理します。clone直後は必要に応じて `git lfs pull` を実行し、PPTXがLFS pointerのままでないことを確認します。Notebook、CSV、PPTXを一括整形・改名・削除しないでください。

2026-07-10時点では、lesson 7の比較用Notebook/PPTXとlesson 8のTitanic CSVに既存の未追跡ファイルがあります。これらは作業中の成果物として扱い、明示的な指示なしに変更、追加登録、削除しません。

## 再現性

- データは可能な限り相対パスで参照します。絶対パスが残る箇所は各lessonのREADMEに記載しています。
- 学習・テスト分割を先に行い、標準化などの前処理は学習データだけでfitします。
- 乱数を使う分割・モデル・可視化はseedを固定します。
- Notebookを変更した場合は先頭から実行し、スライド内の数値、図、モデル名と一致することを確認します。
