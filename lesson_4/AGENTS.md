# AGENTS.md - Lesson 4

## 適用範囲

このファイルは `lesson_4/` に適用し、共通規則は `../AGENTS.md` を継承する。

## 固有ルール

- `Python_Seminar_No.4.ipynb` の2つの絶対パスを既知の不具合として扱い、新しい絶対パスを追加しない。
- `Material_Lifespan_Dataset_encoded_sklearn.csv` はこのlessonにある。`feature_engineering_dataset.csv` は現在 `../lesson_6/` にだけあるため、内容確認なしに複製・移動しない。
- 多項式特徴量はtrain/test分割との順序を確認し、テストデータで前処理やモデルをfitしない。既存Notebookは全training dataを標準化してから `GridSearchCV` へ渡すため、修正時はscalerとSVRを同じ `Pipeline` に入れ、CV foldごとに前処理をfitする。
- SVRの `C`、`epsilon`、`gamma` とscoringを変更した場合、探索範囲と選択結果を記録する。

## 完了条件

対象データの実在場所、相対参照、分割件数、最良パラメータ、R2/RMSE/MAEを確認する。既知の絶対パスを残した場合は未検証範囲として報告する。
