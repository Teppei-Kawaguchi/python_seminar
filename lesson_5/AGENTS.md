# AGENTS.md - Lesson 5

## 適用範囲

このファイルは `lesson_5/` に適用し、共通規則は `../AGENTS.md` を継承する。

## 固有ルール

- `Python_Seminar_No.5.ipynb` には `/Users/k-teppei/Documents/Python Seminar/diabetes.csv` という絶対パスと、その読込失敗出力が残っている。新しい絶対パスへ置換せず、修正時は同じディレクトリの `diabetes.csv` を相対参照する。
- 目的変数は `Outcome` である。クラス比を確認し、train/test分割とCVでは層化を維持する。
- kNNの標準化はpipeline内で学習foldごとにfitし、全データの事前標準化による漏洩を避ける。
- Accuracy単独で結論を出さず、Precision、Recall、F1、ROC-AUC、PR-AUC、混同行列を用途に合わせて確認する。
- 2つのNotebookと2つのPPTXは別版として維持し、ユーザー指定なしに統合・上書きしない。

## 完了条件

データ参照を解決したうえで、クラス比、層化条件、最良パラメータ、テスト指標、混同行列を確認し、スライドのモデル名と数値を同期する。
