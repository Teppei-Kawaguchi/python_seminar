# Lesson 3: 線形回帰と正則化

Bostonデータを使い、最小二乗法、Lasso回帰、PLS回帰の原理と特徴、標準化、Lassoによる特徴量選択、交差検証、XGBoostとの比較を扱います。

## 主なファイル

- [`Python_Seminar_No.3_homework.ipynb`](Python_Seminar_No.3_homework.ipynb): 演習Notebook
- [`Python_Seminar_No.3(2)_homework.ipynb`](<Python_Seminar_No.3(2)_homework.ipynb>): 別版の演習Notebook
- [`boston.csv`](boston.csv): 回帰データ
- `第3回_Pythonセミナー.pptx`: 発表資料
- `main.py`: uv初期化時の表示用雛形

2つのNotebookはどちらも追跡中です。片方を自動的な正本と決めたり、一方の内容で他方を上書きしたりせず、依頼で指定された版を使います。

## 既知の評価上の制約

既存Notebookは全training dataで標準化してから `LassoCV` の内部交差検証を行います。test dataは標準化に使っていませんが、CVの各validation foldから見れば前処理情報が混入します。現在の指標を厳密な未見性能として過大解釈せず、修正時はscalerをfold内でfitするCV構成へ変更してください。

## 実行

```bash
uv lock --check
uv sync --frozen
```

Notebookは `boston.csv` を相対パスで読みます。先頭から実行し、LassoCVの選択alpha、係数、train/test指標を確認してください。
