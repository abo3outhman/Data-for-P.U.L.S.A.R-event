# 🪨 PULSAR Hackathon — Power Stone
## Technical Sheet (Participant Guide)

---

## 1. The Problem (In Simple Words)

You are a Data Scientist working for a global retail company.
The company sells products across many countries and wants to **understand its profit**.

Your job has **two parts**:

### 🎯 Part A — Predict the Profit (50%)
For every transaction (row) in the test set, **predict the Profit** value.
This is a regression problem — the closer your prediction is to the real profit, the better your score.

### 📊 Part B — Business Report (35%)
Using the **training data**, find:
- Which **Category** is the most profitable and which is the least profitable.
- Inside each Category, look at all the **Sub-Categories** — use them to **explain why** the Category is good or bad.
- Write a PDF report with your findings + **5 recommendations** to help the company increase its profit.

### 🎤 Part C — Presentation (15%)
On the final day, present your work in **5 minutes**:
- What you predicted and how.
- Your business insights.
- Your recommendations.

---

## 2. Files Provided

| File | Description |
|------|-------------|
| `train.csv` | Training data (with the `Profit` column) |
| `test.csv` | Test data (**without** `Profit`) — predict it |
| `sample_submission.csv` | Submission format template |
| `technical_sheet.md` | This guide |

---

## 3. The Dataset

**Source:** Global Superstore Sales (2011–2014)

**Size:** ~50,000 transactions

### Columns (24)

#### 🛒 Order Information
| Column | Type | Description |
|--------|------|-------------|
| `Row ID` | int | Unique row identifier |
| `Order ID` | str | Unique order ID (one order may have multiple rows) |
| `Order Date` | date | When the order was placed |
| `Ship Date` | date | When the order was shipped |
| `Ship Mode` | str | Shipping method (Standard Class, Second Class, First Class, Same Day) |
| `Order Priority` | str | Low / Medium / High / Critical |

#### 👤 Customer Information
| Column | Type | Description |
|--------|------|-------------|
| `Customer ID` | str | Unique customer ID |
| `Customer Name` | str | Customer name |
| `Segment` | str | Consumer / Corporate / Home Office |
| `City` | str | Customer's city |
| `State` | str | Customer's state |
| `Country` | str | Customer's country |
| `Postal Code` | str | Postal code (may have missing values) |
| `Market` | str | Broad market (e.g. APAC, EU, US) |
| `Region` | str | Geographic region |

#### 📦 Product Information
| Column | Type | Description |
|--------|------|-------------|
| `Product ID` | str | Unique product ID |
| `Category` | str | Main category: **Furniture / Office Supplies / Technology** (3 values) |
| `Sub-Category` | str | Sub-category inside the main one (~17 values: Chairs, Tables, Storage, Art, Binders, Phones, etc.) |
| `Product Name` | str | Full product name |

#### 💰 Sales Information
| Column | Type | Description |
|--------|------|-------------|
| `Sales` | float | Total sale amount (USD) |
| `Quantity` | int | Number of units sold |
| `Discount` | float | Discount applied (0.0 – 0.85) |
| `Profit` | float | **🎯 TARGET** — Profit for this transaction (USD). Can be negative (loss). |
| `Shipping Cost` | float | Shipping cost (USD) |

> ⚠️ **Note:** `Profit` is **removed from `test.csv`**. You must predict it.

---

## 4. Scoring — How You Will Be Evaluated

### 📈 Part A: Prediction Score (50%)

**Metric:** **RMSE** (Root Mean Squared Error)

**Formula:**
```
RMSE = sqrt( mean( (y_true - y_predicted)^2 ) )
```

**Why RMSE?**
- The profit values are large (in thousands of USD).
- RMSE penalizes big errors heavily.
- It's the standard metric for regression problems.

**Important:**
- The profit can be **negative** (when the company loses money).
- Do **not** apply `log()` to your predictions — submit the raw profit values.
- Lower RMSE = better score.

#### Submission Format
Submit a CSV file named `submission.csv` with this exact format:

```csv
Row ID,Predicted Profit
1,123.45
2,-45.67
3,890.12
...
```

- One row per test row.
- `Row ID` must match the test set.
- `Predicted Profit` is your predicted value (float).

---

### 📊 Part B: Business Report (35%)

Submit a **PDF file** named `report.pdf` containing:

#### Section 1: Executive Summary (½ page)
- Brief overview of what you did.
- Your top 3 findings in bullet points.

#### Section 2: EDA Insights (1–2 pages)
- Distribution of `Profit` (with chart).
- Profit by `Category` (with chart).
- Profit by `Region` or `Market` (with chart).
- Any other insight you found interesting.

#### Section 3: Category Analysis (1–2 pages)

For **each of the 3 Categories** (Furniture, Office Supplies, Technology):

1. Is it profitable or losing money? (Total profit + average profit)
2. Which **Sub-Categories inside it** are the most profitable?
3. Which **Sub-Categories inside it** are the least profitable?
4. **Explain why** — give at least **3 reasons** based on the data
   (e.g. "Chairs has high discount → low margin", "Phones has high volume → high total profit")

> 💡 Use Sub-Categories to **explain** why the Category is good or bad.
> Don't just list numbers — tell the story.

#### Section 4: Recommendations (½–1 page)
Give **5 actionable recommendations** to the company to increase profit. Each must be:
- Specific (not "improve sales")
- Based on data (cite your numbers)
- Realistic

**Example of a good recommendation:**
> "Reduce discounts on Tables from 30% to 15%. Tables generated $X in losses because of high discounts (avg 30%) and low quantity per order (avg 2)."

**Example of a bad recommendation:**
> "Improve marketing." ❌ (too vague)

#### Section 5: Limitations (¼ page)
- What couldn't you solve?
- What assumptions did you make?

#### 🎁 Bonus (+5 points, optional)
For each Sub-Category, identify the **Top-3** and **Bottom-3 products** by total profit.
Each product must have **at least 20 orders** (to avoid outliers).
Mention 1 reason for each.

---

### 🎤 Part C: Presentation (15%)

On the final day, present your work in **5 minutes** (3 min presentation + 2 min Q&A).

**What to cover:**
1. Your ML approach (model + key features).
2. Your top business finding.
3. Your best recommendation.

**Judges will evaluate:**
- Clarity of explanation.
- Storytelling (don't just read numbers).
- Quality of visuals (1–2 charts maximum).
- Answers to Q&A.

---

## 5. Suggested Workflow

| Phase | Task | Time |
|-------|------|------|
| 1 | Load data, do EDA, understand the columns | 1 hour |
| 2 | Handle missing values + encode categoricals | 1 hour |
| 3 | Build ML model (try: Linear, Random Forest, XGBoost, LightGBM) | 2 hours |
| 4 | Validate with K-Fold CV, tune hyperparameters | 1 hour |
| 5 | Predict on test set → `submission.csv` | 30 min |
| 6 | Analyze Categories + Sub-Categories | 1.5 hours |
| 7 | Write the PDF report | 1.5 hours |
| 8 | Prepare the presentation | 1 hour |
| **Total** | | **~8.5 hours** |

---

## 6. Rules

1. **No external data** — use only the provided files.
2. **AI tools allowed** for guidance and code help, but you must understand your solution.
3. **No copying** from other teams.
4. **Submission deadline:** Saturday 10:00 AM.
5. **Late submissions** lose 10% per hour.
6. The `Profit` column in `test.csv` is **secret** — do not try to find it online.
7. You must submit **3 files**:
   - `submission.csv` (predictions)
   - `report.pdf` (business report)
   - `notebook.ipynb` or `script.py` (your code, optional but recommended)

---

## 7. Evaluation Summary

| Part | Weight | What's evaluated |
|------|--------|------------------|
| 📈 Prediction | 50% | RMSE on test set |
| 📊 Report | 35% | EDA + Category/Sub-Category analysis + Recommendations |
| 🎤 Presentation | 15% | Clarity + Storytelling + Q&A |
| 🎁 Bonus | +5% | Product-level analysis inside Sub-Categories |

---

## 8. Tips for Success

✅ **Do:**
- Spend time on EDA — it's the foundation of everything.
- Try multiple models and pick the best.
- Use cross-validation to avoid overfitting.
- Explain your findings in plain business language.
- Use charts to communicate.

❌ **Don't:**
- Don't ignore missing values.
- Don't apply `log()` to profit (it has negative values).
- Don't just copy-paste from ChatGPT without understanding.
- Don't spend all your time on ML and forget the report.
- Don't write vague recommendations.

---

## 9. The Winning Team

The winning team will:
1. Have a **low RMSE** on the prediction.
2. Show **clear understanding** of the business in the report.
3. Give **specific, data-driven recommendations**.
4. Present their work **clearly and confidently**.

Good luck! 🪨

---

*Power Stone — PULSAR Hackathon, Data Space Club, ENSSEA*
