# 🪨 PULSAR Hackathon — Soul Stone
## Technical Sheet (Participant Guide)

---

## 1. The Problem

You are given a dataset of **course reviews** written by students who completed online courses. Each review has been assigned a rating from **1 to 5** (where 1 = very negative, 5 = very positive).

Your task is to **build a model that can predict the rating (1–5) of a review based only on its text**.

This is a **multi-class text classification problem**:
- **Input:** A text review (in English).
- **Output:** A rating from 1 to 5.

---

## 2. Files Provided

| File | Description |
|------|-------------|
| `soul_train.csv` | Training data — contains `Id`, `Review`, `Rate` |
| `soul_test.csv` | Test data — contains `Id`, `Review` (**`Rate` is hidden**) |
| `sample_submission.csv` | Submission format template |
| `technical_sheet.md` | This guide |

---

## 3. The Dataset

### Source
Real Coursera course reviews from students around the world.

### Columns

| Column | Type | Description |
|--------|------|-------------|
| `Id` | int | Unique identifier for each review |
| `Review` | str | The full text of the student's review |
| `Rate` | int | The rating given by the student (**1–5**). **This is your target.** |

> ⚠️ `Rate` is **removed from `soul_test.csv`**. You must predict it.

### Rating Distribution (Training Set)

The dataset is **imbalanced**. You should be aware of this when designing your model.

| Rate | Meaning |
|------|---------|
| 1 | Very negative |
| 2 | Negative |
| 3 | Neutral |
| 4 | Positive |
| 5 | Very positive |

---

## 4. What You Must Do

### 🎯 Build a Classifier
Predict the `Rate` (1, 2, 3, 4, or 5) for every review in the test set.

### 📤 Submit Predictions
Submit a CSV file with your predicted ratings for the test set.

---

## 5. Evaluation Metric

Your submission will be scored using:

### **Macro F1-Score**

$$F1_{\text{macro}} = \frac{1}{5} \sum_{i=1}^{5} F1_i$$

Where for each class $i$:

$$F1_i = 2 \cdot \frac{Precision_i \cdot Recall_i}{Precision_i + Recall_i}$$

### Why Macro F1?
- It treats **all classes equally** — including minority classes (Rate=1, Rate=2).
- A model that only predicts "5" will get a low score.
- It is robust to class imbalance.

**Higher is better. Maximum = 1.0**

---

## 6. ⚠️ STRICT RULES — READ CAREFULLY

### 🚫 FORBIDDEN (Using any of these = DISQUALIFICATION)

| # | Forbidden Technique |
|---|---------------------|
| 1 | **Deep Learning models** (Neural Networks, MLP, DNN) |
| 2 | **Recurrent Neural Networks** (RNN, LSTM, GRU) |
| 3 | **Convolutional Neural Networks** (1D CNN for text) |
| 4 | **Transformers** (BERT, GPT, RoBERTa, DistilBERT, T5, XLNet, ELECTRA, etc.) |
| 5 | **Pre-trained language models** of any kind |
| 6 | **Word embeddings from neural models** (Word2Vec, GloVe, FastText) — these are allowed only if you train them yourself from scratch, NOT if you load pre-trained versions |
| 7 | **Any deep learning framework** as the final classifier (TensorFlow, PyTorch, Keras) |
| 8 | **AI-as-a-service APIs** (OpenAI, Claude, Gemini, etc.) to classify the reviews |

### ❌ Using Deep Learning = **CHEATING**

> This challenge is designed to test your ability to work with **classical NLP and classical Machine Learning**.
> If you submit a Deep Learning model, your team will be **disqualified immediately**, regardless of your score.

---

## 7. ✅ ALLOWED Techniques

You **must** use classical approaches. The following are allowed and encouraged:

### 📝 Text Preprocessing (All Allowed)
- Tokenization (split text into words)
- Lowercasing
- Removing punctuation
- Removing numbers
- Removing stopwords
- Stemming (Porter, Snowball, Lancaster)
- Lemmatization
- Handling emojis (remove or convert to text)
- Handling HTML tags / URLs
- Custom text cleaning

### 🧮 Text Representation (All Allowed)
- **Bag of Words** (CountVectorizer)
- **TF-IDF** (TfidfVectorizer)
- **N-grams** (unigrams, bigrams, trigrams)
- **Character n-grams**
- **Hashing vectorizer**
- **Custom features** (text length, word count, punctuation count, sentiment lexicon features, etc.)
- **Lexicon-based features** (VADER, TextBlob sentiment scores — only as features, not as the final classifier)

### 🤖 Classical ML Models (All Allowed)
- **Naive Bayes** (Multinomial, Bernoulli, Gaussian)
- **Logistic Regression**
- **Support Vector Machines** (LinearSVC, SVC with RBF kernel)
- **Decision Trees**
- **Random Forest**
- **Gradient Boosting** (XGBoost, LightGBM, CatBoost)
- **K-Nearest Neighbors**
- **Ridge Classifier**
- **Passive-Aggressive Classifier**
- **Any other classical ML model from scikit-learn or similar**

### 🔧 Other Allowed Practices
- Cross-validation (K-Fold, Stratified K-Fold)
- Hyperparameter tuning (GridSearchCV, RandomizedSearchCV)
- Feature selection (chi-squared, mutual information)
- Ensemble methods (VotingClassifier, StackingClassifier)
- Handling class imbalance (class_weight, SMOTE, undersampling)

---

## 8. Submission Format

Submit a CSV file named `submission.csv` with this exact format:

```csv
Id,Rate
1,5
2,3
3,1
...
```

- One row per test review.
- `Id` must match the test set exactly.
- `Rate` must be an **integer** between 1 and 5.
- Do **not** include any header other than `Id,Rate`.
- Do **not** submit probabilities — submit the final class.

### Example
```
Id,Rate
1,5
2,4
3,2
4,1
5,5
```

---

## 9. Suggested Workflow

| Phase | Task | Time |
|-------|------|------|
| 1 | Load data, explore distribution | 30 min |
| 2 | Text preprocessing (cleaning, tokenization) | 1 hour |
| 3 | Text representation (TF-IDF with n-grams) | 30 min |
| 4 | Train baseline model (Naive Bayes / Logistic Regression) | 30 min |
| 5 | Try multiple models, compare | 1 hour |
| 6 | Hyperparameter tuning + cross-validation | 1 hour |
| 7 | Handle class imbalance | 30 min |
| 8 | Final predictions + submission | 30 min |
| **Total** | | **~5.5 hours** |

---

## 10. Submission Checklist

Before submitting, verify:

- [ ] You did NOT use any Deep Learning model.
- [ ] You did NOT use pre-trained language models (BERT, GPT, etc.).
- [ ] You did NOT use pre-trained word embeddings.
- [ ] Your `submission.csv` has the exact format shown above.
- [ ] `Id` values match the test set.
- [ ] `Rate` values are integers between 1 and 5.
- [ ] The file is named `submission.csv`.
- [ ] You submit 3 files:
  - `submission.csv` (predictions)
  - `notebook.ipynb` or `script.py` (your code, **required for verification**)
  - `report.pdf` (short report, 1–2 pages)

---

## 11. Files to Submit

| File | Required | Description |
|------|----------|-------------|
| `submission.csv` | ✅ Yes | Your predictions |
| `notebook.ipynb` or `script.py` | ✅ Yes | Your full code (judges will check for DL usage) |
| `report.pdf` | ✅ Yes | Brief report (1–2 pages): your approach, preprocessing, model, results |

> ⚠️ If your code is not submitted, your team will be **disqualified**. Judges must verify that no Deep Learning was used.

---

## 12. Evaluation Summary

| Component | Weight |
|-----------|--------|
| Macro F1-Score on test set | 70% |
| Code quality + clarity | 15% |
| Report quality | 15% |

---

## 13. Final Reminder

> 🚨 **This is a Classical ML + Classical NLP challenge.**
> Using Deep Learning in any form = **cheating = disqualification.**
>
> Be creative with text preprocessing.
> Be smart with feature engineering.
> Be rigorous with cross-validation.
>
> The best team is not the one with the fanciest model — it's the one with the cleanest approach.

Good luck! 🪨

---

*Soul Stone — PULSAR Hackathon, Data Space Club, ENSSEA*
