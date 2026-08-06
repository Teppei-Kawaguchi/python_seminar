# Lesson 6: PCAとクラスタリング

手書き数字画像を784次元のpixelデータとして扱い、PCA、UMAPまたはt-SNE、階層的クラスタリング、k-meansで可視化・分類構造を調べる回です。

## 主なファイル

- [`Python_Seminar_No.6.ipynb`](Python_Seminar_No.6.ipynb): 授業用Notebook
- [`assignment.cord.第6回.ipynb`](assignment.cord.第6回.ipynb): 詳細版の課題Notebook
- [`feature_engineering_dataset.csv`](feature_engineering_dataset.csv): lesson 4のNotebookが参照する同名データ
- [`Material_Lifespan_Dataset_encoded_sklearn.csv`](Material_Lifespan_Dataset_encoded_sklearn.csv): 付属データ
- `第6回Pythonセミナー_可視化クラスタリングHY (1).pptx`: 発表資料
- `main.py`: uv初期化時の表示用雛形

## 既知の制約

両Notebookは `MNICT_train.csv` または `MNICT_train.csv.zip` を参照しますが、現在そのzipはこのlessonではなく `../lesson_7/MNICT_train.csv.zip` にあります。ファイル名は実物どおり `MNICT` です。Notebookをそのまま `lesson_6/` から実行するとデータ読込で停止します。

`assignment.cord.第6回.ipynb` には相対パス候補に加え、別ユーザー環境の `/Users/t-shuichi/...` がfallbackとして残っています。配置変更やデータ複製は行っていません。

この詳細版Notebookは、入力データと同じディレクトリへ `pca_loadings.csv`、`pca_score.csv`、UMAP・クラスタリング関連など複数のCSVを生成します。Google Drive上の原本を直接使わず、出力場所を確認して `/tmp` の作業コピーで検証してください。また、正解ラベル用の `MNICT_train_label.csv` は現在存在しません。前半の一部処理はラベル比較をスキップできますが、後半では `FileNotFoundError` となるため、全セル完走済みとは扱えません。

## 実行

```bash
uv lock --check
uv sync --frozen
```

データ参照を明示的に解決した後、まず行数を制限して動作を確認します。全件のPCA、UMAP、pair plot、階層クラスタリングは計算時間とメモリ使用量が大きくなります。
