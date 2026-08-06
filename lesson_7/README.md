# Lesson 7: Applicability Domain

Boston Housingの回帰モデルについて、学習データからの距離を使ってApplicability Domain（AD）内外を判定し、予測誤差と信頼性を評価する回です。

## 追跡中の中心資料

- [`Python_Seminar_No.7.ipynb`](Python_Seminar_No.7.ipynb): 第7回Notebook
- [`applicability_domain_boston.ipynb`](applicability_domain_boston.ipynb): kNN距離を中心としたAD解析
- [`boston.csv`](boston.csv): 回帰データ
- `適用ドメイン.pptx`: 発表資料
- `適用ドメイン_説明用_シンプル_2026-07-03.pptx`: 説明用資料
- [`MNICT_train.csv.zip`](MNICT_train.csv.zip): lesson 6が参照する手書き数字データ。AD解析の入力ではない

## 作業中の比較版

2026-07-10時点で、次は未追跡のユーザー成果物です。

- `applicability_domain_boston (1).ipynb`: コピー名の詳細版
- `applicability_domain_boston_method_comparison.ipynb`: kNN、Mahalanobis、PCA再構成誤差、One-Class SVM、Isolation Forest、LOFの比較
- `applicability_domain_boston_model_comparison.ipynb`: 同じAD判定下での回帰モデル比較
- `applicability-domain_2026_07_07.pptx` と2つのcomparison supplement PPTX

複数版の最終的な正本はファイル配置だけでは確定できません。編集・発表時は対象ファイルを明示し、未追跡版を追跡中Notebookへ自動統合しないでください。

## 既知の評価上の制約

`Python_Seminar_No.7.ipynb` と `applicability_domain_boston.ipynb` は、複数モデルをhold-out testで比較し、test RMSEが最小のモデルを同じtestのAD解析に再利用します。このため、記録済みのtest/AD指標はモデル選択の影響を受けます。未見データへの最終性能として断定せず、厳密な修正ではtraining data内のvalidationまたはnested CVでモデルを固定してからtestを一度だけ評価してください。

## 実行

```bash
UV_CACHE_DIR=/tmp/uv-cache-lesson-7 uv lock --check
UV_CACHE_DIR=/tmp/uv-cache-lesson-7 uv sync --frozen
```

このlessonだけ `uv.toml` の既定値が `.uv-cache` を指すため、上記のようにDrive外のcacheを明示します。Notebookは `boston.csv` を相対パスで読み、学習データで標準化とADしきい値を決めてからテストデータを評価します。
