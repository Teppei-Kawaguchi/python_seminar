# AGENTS.md - Lesson 7

## 適用範囲

このファイルは `lesson_7/` に適用し、共通規則は `../AGENTS.md` を継承する。

## 固有ルール

- 追跡中の中心版、未追跡コピー、手法比較版、モデル比較版を別成果物として維持する。対象版が曖昧なまま相互上書き、統合、改名しない。
- `boston.csv` がAD解析の入力である。`MNICT_train.csv.zip` はlesson 6用なので混同しない。
- scaler、共分散、PCA、近傍探索器、外れ値検出器、ADしきい値は学習データだけでfitまたは算出する。
- `Python_Seminar_No.7.ipynb` と `applicability_domain_boston.ipynb` は、同じhold-out testのRMSEで候補モデルを選び、そのtestをAD解析にも再利用している。既存結果を未見データへの不偏評価とせず、修正時はtraining data内のvalidationまたはnested CVでモデルを選び、最終testはモデル固定後に一度だけ評価する。
- AD内外の件数が少ない場合、RMSE/R2の差を一般化せず件数を併記する。距離の定義、近傍数、percentile、contamination、seedを記録する。
- PPTXを変更するときは対応Notebook、データ分割、モデル、しきい値、図の軸・単位、数値を確認する。

## 完了条件

対象版、Git追跡状態、モデル選択用データ、最終評価用データ、AD手法と設定、内外件数・誤差を報告し、既存の未追跡6ファイルを保持する。
