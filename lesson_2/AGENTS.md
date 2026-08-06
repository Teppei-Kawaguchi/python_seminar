# AGENTS.md - Lesson 2

## 適用範囲

このファイルは `lesson_2/` に適用し、共通規則は `../AGENTS.md` を継承する。

## 固有ルール

- `Python_Seminar_No.2_homework .ipynb` と `Python_seminar_NN_rdkit_descriptors.csv` を一組として扱う。末尾空白を含むNotebook名を勝手に変更しない。
- 授業の主眼は機械学習フローである。説明コメントの課題部分を、根拠なく完成済みにしない。
- train/test分割と早期停止用validationの役割を混同せず、テスト指標は最終評価にだけ使う。
- 既存の `random_state=42`、目的変数、評価指標を変更する場合は理由と結果差を記録する。

## 完了条件

CSVが相対パスで読めること、分割件数、学習・テスト指標、主要な図が再現できることを確認する。
