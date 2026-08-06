# Lesson 5: クラス分類

糖尿病データを使い、k近傍法（kNN）とRandom Forestによる二値分類、層化交差検証、ハイパーパラメータ探索、複数の分類指標を扱います。

## 主なファイル

- [`Python_Seminar_No.5.ipynb`](Python_Seminar_No.5.ipynb): kNNとRandom Forestの比較Notebook
- [`pysemi5_kazuma_g2.ipynb`](pysemi5_kazuma_g2.ipynb): 別の演習Notebook
- [`diabetes.csv`](diabetes.csv): 分類データ
- `第5回Pythonセミナー_.pptx`: 発表資料
- `第5回Pythonセミナー_次回予告 .pptx`: 次回予告
- `main.py`: uv初期化時の表示用雛形

中心Notebookは `Outcome` を目的変数とし、kNNでは標準化を含むpipelineを使います。AccuracyだけでなくPrecision、Recall、F1、ROC-AUC、混同行列、ROC/PR曲線を確認します。

## 既知の制約

`Python_Seminar_No.5.ipynb` は `/Users/k-teppei/Documents/Python Seminar/diabetes.csv` という端末固有の絶対パスを参照し、現在は `FileNotFoundError` の出力も保存されています。実行前に、同じディレクトリの `diabetes.csv` を相対参照するよう修正する必要があります。今回はNotebook自体を変更していません。

## 実行

```bash
uv lock --check
uv sync --frozen
```

データ参照を解決してからNotebookを `lesson_5/` で開き、先頭から実行してください。2つのNotebookは自動統合せず、指定された版を編集します。
