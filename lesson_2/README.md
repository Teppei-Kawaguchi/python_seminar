# Lesson 2: 機械学習の基本フロー

表形式データの読み込み、説明変数と目的変数の分離、train/test分割、回帰モデルの学習、予測性能の評価を学ぶ回です。演習ではRDKit descriptorデータとXGBoostを扱い、MAE、RMSE、R2、予測値-実測値プロットを確認します。

## 主なファイル

- [`Python_Seminar_No.2_homework .ipynb`](<Python_Seminar_No.2_homework .ipynb>): 予習・演習Notebook
- [`Python_seminar_NN_rdkit_descriptors.csv`](Python_seminar_NN_rdkit_descriptors.csv): 演習データ
- `第2回_Pythonセミナー.pptx`: 発表資料
- `第2回Python セミナー_次回予告.pptx`: 次回予告
- `main.py`: uv初期化時の表示用雛形

NotebookはCSVを同じディレクトリから相対パスで読み、`random_state=42` で分割します。学習・評価、XGBoostの早期停止、特徴量重要度までが主な流れです。

## 実行

```bash
uv lock --check
uv sync --frozen
```

Notebookを `lesson_2/` から開き、先頭セルから実行してください。共通ルールは [../README.md](../README.md) を参照してください。
