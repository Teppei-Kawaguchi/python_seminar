# Lesson 4: 特徴量設計とSVR

二乗・三乗特徴量とLasso回帰、材料寿命データに対するSVR、GridSearchCVによるハイパーパラメータ探索を扱います。

## 主なファイル

- [`Python_Seminar_No.4.ipynb`](Python_Seminar_No.4.ipynb): LassoとSVRの演習Notebook
- [`Material_Lifespan_Dataset_encoded_sklearn.csv`](Material_Lifespan_Dataset_encoded_sklearn.csv): SVR用データ
- [`Python_seminar_NN_rdkit_descriptors.csv`](Python_seminar_NN_rdkit_descriptors.csv): 付属データ
- `第4回_Pythonセミナー_角田_v2.pptx`: 発表資料
- `main.py`: uv初期化時の表示用雛形

## 既知の制約

Notebookには次の端末固有の絶対パスが残っているため、現在のままでは別環境で再現できません。

- `/Users/k-teppei/Documents/Python Seminar/feature_engineering_dataset.csv`
- `/Users/k-teppei/Documents/Python Seminar/Material_Lifespan_Dataset_encoded_sklearn.csv`

後者はこのlesson内にあります。前者と同名のファイルは現在 `../lesson_6/feature_engineering_dataset.csv` にあります。今回は配置もNotebookも変更していません。修正タスクではデータの同一性を確認してから `pathlib.Path` による相対参照へ変更してください。

既存NotebookのSVR探索は、全training dataで標準化してから `GridSearchCV` を行います。test dataはfitに使っていませんが、CV validation foldの情報がscalerへ入ります。厳密に評価する修正では、scalerとSVRを `Pipeline` にまとめ、各foldのtraining部分だけで標準化してください。

## 実行

```bash
uv lock --check
uv sync --frozen
```

パス問題を解消した環境で先頭から実行し、LassoとSVRそれぞれの分割、標準化、R2、RMSE、MAEを確認します。
