# AGENTS.md - Lesson 3

## 適用範囲

このファイルは `lesson_3/` に適用し、共通規則は `../AGENTS.md` を継承する。

## 固有ルール

- 2つの `Python_Seminar_No.3*_homework.ipynb` は別版として保存する。版の統合・削除は明示指示がある場合だけ行う。
- `boston.csv` の列、目的変数、indexの扱いを実データで確認し、別のBoston Housing配布物へ無断で置換しない。
- テストデータによるalpha選択をしない。既存Notebookは全training dataを標準化してから `LassoCV` の内部CVへ渡すため、CV validation foldの情報がscalerへ入る。修正時は、foldごとに前処理をfitできる `Pipeline` と外側のCV探索、または同等のfold分離を使う。
- 線形モデルとXGBoostの結果を比べるときは、同じ分割と同じ評価指標を使う。

## 完了条件

対象Notebookの版、分割条件、選択alpha、非ゼロ係数数、回帰指標を確認し、PPTX変更時は同じ数値へ同期する。
