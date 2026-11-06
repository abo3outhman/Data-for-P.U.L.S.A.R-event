# 🪨 PULSAR Hackathon — Time Stone
## Participant Guide: Dataset Description

> **Challenge:** Predict the **Profit** (`Profit`) for each transaction in the test set.
> **Type:** Supervised Regression (Multivariate)
> **Target:** `Profit` column (removed from `test.csv`)

---

## 📦 Files Provided

| File | Description |
|------|-------------|
| `train.csv` | Training data (70%) — includes the target `Profit` |
| `test.csv`  | Test data (30%) — **without** the target `Profit` |
| `sample_submission.csv` | Submission template (format to follow) |
| `data_description.md`   | This guide |

---

## 🎯 The Target

### `Profit` *(float, IDR)*
- Net profit for the transaction.
- Computed as: `Item Price Amount − Material Cost`
- **Available in `train.csv` only.** You must predict it for every row in `test.csv`.

---

## 📑 Column-by-Column Description

### 🔹 1. Transaction Identifiers

| # | Column | Type | Description |
|---|--------|------|-------------|
| 1 | `Invoice Code` | str | Unique invoice ID (e.g. `SI24100331`). Multiple items can share the same invoice. |
| 2 | `Customer Code` | str | Anonymized customer ID (e.g. `P0535`, `T-R`). Some customers are walk-in. |

### 🔹 2. Product Information

| # | Column | Type | Description |
|---|--------|------|-------------|
| 3 | `Item Name` | str | Product/service name (e.g. `BANNER OUTDOOR 280`). Free text. |
| 4 | `Item Quantity` | float | Quantity sold. Supports decimals (e.g. `4.4` meters of banner). |
| 5 | `Item Price` | float | Unit price per item/meter (IDR). |
| 6 | `Item Price Amount` | float | Total price = `Item Quantity × Item Price` (IDR). |
| 8 | `Item Category` | str | Derived category: `Banner`, `Sticker`, `ID & Lanyard`, `Stamp`, `Paper & Board`, `Photo & Poster`, `Apparel`, `Printed Docs`, `Souvenir`, `Other`. |
| 9 | `Material Cost` | float | Cost of raw materials for the item (IDR). **Key predictor of `Profit`.** |

### 🔹 3. Time Information

| # | Column | Type | Description |
|---|--------|------|-------------|
| 7 | `Transaction At` | datetime | Timestamp (`YYYY-MM-DD HH:MM:SS`). |
| 17 | `hour` | int | Hour of the day (0–23). |
| 18 | `day_of_week` | int | Day of week (0=Monday, 6=Sunday). |
| 19 | `day_of_month` | int | Day of month (1–31). |
| 20 | `month` | int | Month (1–12). |
| 21 | `quarter` | int | Quarter (1–4). |
| 22 | `week_of_year` | int | ISO week number (1–53). |
| 23 | `is_month_start` | int | 1 if first days of month, else 0. |
| 24 | `is_month_end` | int | 1 if last days of month, else 0. |
| 15 | `Is_Weekend` | int | 1 if Saturday/Sunday, else 0. |
| 16 | `Is_Holiday` | int | 1 if Indonesian public holiday, else 0. |

### 🔹 4. Customer & Channel

| # | Column | Type | Description |
|---|--------|------|-------------|
| 11 | `Customer Type` | str | `Individual`, `Small Business`, `Corporate`, `Walk-in`. |
| 12 | `Order Channel` | str | `WhatsApp`, `Instagram`, `Walk-in`, `Email`, `Website`. |
| 13 | `Payment Method` | str | `Cash`, `Transfer`, `QRIS`, `Credit`. |
| 14 | `Discount (%)` | float | Discount applied. 0 if no discount. |
| 40 | `channel_prepaid` | int | 1 if `Payment Method ∈ {Transfer, QRIS, Credit}`. |
| 41 | `is_corporate` | int | 1 if `Customer Type == 'Corporate'`. |

### 🔹 5. Text-Derived Features (from `Item Name`)

| # | Column | Type | Description |
|---|--------|------|-------------|
| 25 | `item_name_length` | int | Character length of `Item Name`. |
| 26 | `item_word_count` | int | Number of words in `Item Name`. |
| 27 | `has_size_keyword` | int | 1 if name contains size markers like `A4`, `F4`, `S/M/L`, `X2`. |
| 28 | `has_number_in_name` | int | 1 if name contains any digit. |

### 🔹 6. Derived Numeric Features

| # | Column | Type | Description |
|---|--------|------|-------------|
| 29 | `price_per_unit_qty` | float | `Item Price / Item Quantity`. |
| 30 | `quantity_log` | float | `log1p(Item Quantity)` — log-transformed quantity. |
| 31 | `amount_log` | float | `log1p(Item Price Amount)` — log-transformed total. |
| 32 | `unit_price_bucket` | str | Price tier: `cheap` / `mid` / `high` / `premium`. |

### 🔹 7. Aggregation Features (per customer / per category)

| # | Column | Type | Description |
|---|--------|------|-------------|
| 33 | `customer_visits` | int | Total number of transactions by this customer. |
| 34 | `customer_avg_amount` | float | Average `Item Price Amount` for this customer. |
| 35 | `customer_max_amount` | float | Maximum `Item Price Amount` for this customer. |
| 36 | `category_avg_price` | float | Average `Item Price` for this `Item Category`. |
| 37 | `category_count` | int | Number of transactions in this `Item Category`. |

### 🔹 8. Operational Flags

| # | Column | Type | Description |
|---|--------|------|-------------|
| 38 | `is_bulk_order` | int | 1 if `Item Quantity` is in the top 10%. |
| 39 | `is_high_value` | int | 1 if `Item Price Amount` is in the top 10%. |

### 🔹 9. Noise (⚠️ Beware)

| # | Column | Type | Description |
|---|--------|------|-------------|
| 42 | `noise_feature` | float | Random Gaussian noise (mean=0, std=1). **No predictive value.** Tests your feature selection. |

---

## ⚠️ Important Notes for Participants

### 1. Missing Values
- Some columns contain `NaN` values (5–15% depending on column).
- You must decide how to handle them: imputation, dropping, or modeling them as a separate category.

### 2. Redundant / Derived Features
Several columns are derived from others (e.g. `Is_Weekend` from `day_of_week`, `amount_log` from `Item Price Amount`). 
- **Not all features help.** Some cause multicollinearity.
- Use feature selection (correlation analysis, VIF, tree-based importance).

### 3. The Noise Trap
`noise_feature` is **purely random**. Including it in your model will hurt your score. Identify and drop it.

### 4. Categorical Encoding
You must encode these categorical columns yourself:
- `Customer Code`, `Item Name`, `Item Category`, `Customer Type`, `Order Channel`, `Payment Method`, `unit_price_bucket`
- High-cardinality: `Customer Code`, `Item Name` — consider target encoding or hashing.

### 5. The Key Predictor
`Material Cost` is strongly correlated with `Profit`. The naive formula `Profit = Item Price Amount − Material Cost` would give a perfect prediction — **but the challenge is to model Profit robustly, including cases where Material Cost is missing or noisy.**

---

## 📤 Submission Format

Submit a CSV file named `submission.csv` with **exactly** this format:

```csv
index,predicted_profit
0,12345.67
1,89000.00
2,1500.50
...
```

- One row per test row (same order as `test.csv`).
- `index` = the row position in `test.csv` (0, 1, 2, ...).
- `predicted_profit` = your predicted `Profit` value (float, IDR).
- Do **not** include any header other than the one shown.

---

## 📊 Evaluation Metrics

Your submission will be scored on **three metrics**:

| Metric | Weight | Interpretation |
|--------|--------|----------------|
| **RMSE** (Root Mean Squared Error) | 40% | Penalizes large errors heavily. |
| **MAE** (Mean Absolute Error) | 30% | Average absolute error in IDR. |
| **MAPE** (Mean Absolute Percentage Error) | 30% | Average percentage error. |

$$\text{Final Score} = 0.40 \cdot \text{RMSE}_{\text{norm}} + 0.30 \cdot \text{MAE}_{\text{norm}} + 0.30 \cdot \text{MAPE}_{\text{norm}}$$

Lower is better.

---

## 🧭 Suggested Workflow

1. **EDA** — Explore distributions, missing patterns, correlations with `Profit`.
2. **Handle NaN** — Impute or drop. Document your strategy.
3. **Encode categoricals** — Choose: one-hot, label, target, or hashing.
4. **Feature selection** — Drop `noise_feature` and redundant columns. Use SHAP / correlation.
5. **Model** — Try: Linear Regression, Random Forest, XGBoost, LightGBM, CatBoost.
6. **Validate** — Use K-Fold CV (with `random_state=42` for reproducibility).
7. **Submit** — Match the exact submission format above.

---

## 🚀 Bonus

- The first team to **identify and drop `noise_feature`** will receive a +2 minute bonus on their final presentation.
- Using advanced feature engineering (target encoding, interaction features) earns extra points.

Good luck! 🪨
