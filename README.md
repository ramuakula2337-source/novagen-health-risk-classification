# NovaGen — Health Risk Classification

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange) ![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-20BEFF)

## Problem Statement

A leading biomedical research institute, **NovaGen Research Labs**, needs a reliable ML system to classify individuals as **healthy** or **at higher health risk** based on physiological measurements, lifestyle factors, and medical history — to support participant selection for clinical trials and longitudinal studies.

---

## Dataset

- **Source:** Kaggle
- **Records:** 9,800 individuals
- **Features:** 23 (Age, BMI, Blood Pressure, Cholesterol, Glucose Level, Sleep Hours, Exercise Hours, Smoking, Alcohol, Mental Health, Physical Activity, Medical History, Blood Group, Diet Type, etc.)
- **Target:** `Target` — health outcome (healthy / unhealthy)

---

## Project Workflow

```
Raw Data → EDA → Preprocessing → Feature Engineering → Model Training → Evaluation → Best Model
```

### Steps
1. **EDA** — Class distribution, correlation heatmap, distribution plots
2. **Preprocessing** — Missing value imputation, one-hot encoding, StandardScaler
3. **Model Training** — 5 models trained and compared
4. **Evaluation** — Recall selected as primary metric (missing a high-risk patient is more dangerous than over-flagging)

---

## Models & Results

| Model | Accuracy | Recall | F1 Score |
|-------|----------|--------|----------|
| Logistic Regression | 81.4% | 82.8% | 81.0% |
| KNN (k=5) | 88.3% | 88.4% | 88.0% |
| Random Forest | **93.7%** | **95.8%** | **94.0%** |
| Gradient Boosting | 93.0% | 94.9% | 93.0% |
| Voting Classifier | 91.6% | 93.1% | 92.0% |

### Best Model: Random Forest
- Accuracy: **93.7%**
- Recall: **95.8%** ← primary metric
- 200 estimators, no max depth constraint

---

## Key Insights

- **Recall chosen over Accuracy** — in healthcare, a false negative (missing a sick person) is far more costly than a false positive
- **Ensemble methods dominated** — Random Forest outperformed Logistic Regression baseline by +13% recall
- **Voting Classifier** underperformed Random Forest alone, suggesting the weaker base models pulled down the ensemble

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python |
| Data Handling | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| ML Models | Scikit-learn |
| Algorithms | Logistic Regression, KNN, Random Forest, Gradient Boosting, Voting Classifier |
| Environment | Jupyter Notebook |

---

## Files

| File | Description |
|------|-------------|
| `novagen.ipynb` | Main notebook — EDA, preprocessing, model training & evaluation |
| `novagen_dataset.csv` | Health records dataset (Kaggle) |
| `README.md` | Project documentation |

---

## How to Run
```bash
# 1. Clone the repository
git clone https://github.com/ramuakula2337-source/novagen-health-risk-classification

# 2. Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn jupyter

# 3. Open the notebook
jupyter notebook novagen.ipynb
```
