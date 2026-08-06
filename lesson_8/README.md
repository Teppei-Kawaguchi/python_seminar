# Lesson 8: Titanic演習（準備中）

Titanicの生存予測演習に向けた準備ディレクトリです。2026-07-10時点ではNotebook、実装、発表スライドはなく、課題仕様も確定していません。

## 現在のファイル

- [`train_titanic.csv`](train_titanic.csv): `Survived` 列を含む712行の学習用候補データ（ヘッダーを除く、未追跡）
- [`test_titanic.csv`](test_titanic.csv): `Survived` 列を含まない179行のテスト用候補データ（ヘッダーを除く、未追跡）
- `pyproject.toml` / `uv.lock`: `ipykernel` のみを宣言した環境雛形
- `main.py`: uv初期化時の表示用雛形

CSVにはPassengerId、客室等級、氏名、性別、年齢、家族人数、チケット、運賃、客室、乗船港などの列があります。通常の分析に必要なpandasやscikit-learnは、現在 `pyproject.toml` に宣言されていません。

## 現在できる確認

```bash
uv lock --check
uv sync --frozen
uv run python main.py
```

これは環境雛形の確認だけです。課題内容、評価方法、提出物、依存関係を推測して実装せず、次の明示指示を待ってください。CSVの未追跡状態も変更しません。
