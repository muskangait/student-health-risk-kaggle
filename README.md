# 🏥 Student Health Risk Prediction

My second Kaggle competition. Predicting whether a student 
is at-risk, unhealthy, or fit based on health and lifestyle data.

**Competition:** Kaggle Playground Series S6E7  
**Public Score:** 0.84951 (Balanced Accuracy)  
**Notebook:** [View on Kaggle](https://www.kaggle.com/code/muskangait/student-health-risk-prediction)  
**First Project:** [Disaster Tweets NLP](https://github.com/YOUR-USERNAME/disaster-tweets-nlp)

---

## About This Project

This is my second ML project. My first was NLP with text data.
This time I worked with structured health data — completely 
different challenge with numeric and categorical columns mixed.

I am a final year CSE student learning AI engineering from scratch.
Every mistake I make is documented here because that is how 
real learning happens.

---

## Dataset

| Detail | Value |
|--------|-------|
| Training rows | 690,088 |
| Test rows | 295,753 |
| Features | 13 |
| Target classes | 3 (at-risk, unhealthy, fit) |
| Class split | 85.9% / 8.4% / 5.8% |
| Missing values | Every single column |

690,088 rows — 90x larger than my first project.

---

## What I Did

### EDA
- Explored class distribution — found severe 86/8/6 imbalance
- Found missing values in every column
- Discovered medium stress level had highest fit proportion
  which surprised me completely

### Preprocessing
Two different strategies for two different data types:

**Numeric columns** — filled with median
Why median not mean? Median is not affected by outliers.

**Categorical columns** — filled with mode
Mode is the most frequent value — makes sense for categories.

Then label encoded all categorical columns because 
models only understand numbers.

### Models

| Model | Balanced Accuracy |
|-------|------------------|
| Logistic Regression | 0.8165 |
| Random Forest | ❌ timed out |
| XGBoost | **0.8576** ← best |

**Final submission score: 0.84951**

---

## Errors I Made

### Error 1 — Random Forest Timeout
Tried Random Forest on 690,088 rows. Never finished.
Had to skip it completely.

**Lesson:** Always check dataset size before choosing model.
Random Forest is too slow above 100k rows.
XGBoost and LightGBM are better choices for large datasets.

### Error 2 — NameError on bal_acc_rf
Random Forest timed out so bal_acc_rf variable was never created.
My comparison cell crashed trying to use it.

**Lesson:** Always verify which models trained successfully
before using their variables in later cells.

---

## What I Learned

- Median vs mean for missing value imputation
- Label encoding categorical columns
- XGBoost — used for the first time
- Balanced accuracy vs F1 score
- Dataset size matters for model selection
- 690k rows — Random Forest fails, XGBoost handles it fine

---

## My Progress Across Projects

| Project | Type | Score | Model |
|---------|------|-------|-------|
| Disaster Tweets | NLP Competition | 0.79037 F1 | Naive Bayes |
| Student Health Risk | Tabular Competition | 0.84951 Balanced Acc | XGBoost |

---

## What I Would Do Differently

- Feature engineering — create new features
- Tune XGBoost with GridSearchCV  
- Try SMOTE for severe class imbalance
- Try LightGBM — faster than XGBoost on large data
- Use cross validation instead of single split

---

## Tech Stack
Python | Pandas | NumPy | Matplotlib | Seaborn |
Scikit-learn | XGBoost
