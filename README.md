# 📺 TV Advertising Impact on Sales

> **Type:** Business Case Analysis · Simple Linear Regression · Hypothesis Testing · Cross-Validation
>
> **Tools:** Python · Pandas · Statsmodels · Scikit-learn · Seaborn · Matplotlib
>
> **Dataset:** [Advertising Dataset (ISLR)](https://www.kaggle.com/datasets/bumba5341/advertisingcsv)

---

## 🏢 Business Problem

A consumer goods company spends across **TV, radio, and print** advertising — but the marketing team had no quantitative answer to a fundamental question:

> *Does TV ad spend actually move sales — and if so, by exactly how much?*

This project isolates the **TV → Sales** relationship and builds a statistically validated model to answer it.

---

## 📐 Approach

| Step | What I Did |
|------|-----------|
| **EDA** | Scatter plot of TV spend vs Sales — confirmed positive linear relationship visually before modelling |
| **OLS Regression** | Fitted simple linear regression using `statsmodels`; extracted intercept, coefficient, and R² |
| **Hypothesis Testing** | Tested significance of both intercept (H₀: β₀ = 0) and slope (H₀: β₁ = 0) using p-values |
| **sklearn Cross-check** | Re-ran model in `sklearn` to verify intercept and coefficient match |
| **5-Fold Cross-Validation** | Computed CV R² scores to confirm generalisation — model not overfitting |
| **Residual Check** | Plotted residual distribution — confirmed normality with mean ≈ 0 |

---

## 📊 Key Findings

**Model:**
```
Sales = 6.97 + 0.055 × TV spend
```

| Metric | Value |
|--------|-------|
| R² (train) | **0.79** |
| CV R² (5-fold avg) | **0.792** |
| Intercept p-value | < 0.001 ✅ significant |
| TV coefficient p-value | < 0.001 ✅ significant |
| Residuals | Normally distributed, mean ≈ 0 ✅ |

- **Every $1,000 increase in TV spend → ~55 additional units sold**
- TV alone explains **79% of sales variation** — a strong, statistically proven driver
- CV R² ≈ Train R² → model generalises well, not overfitting
- Remaining **21% unexplained** → radio and print likely contribute too

---

## 💡 Business Recommendation

> TV is validated as a strong sales driver. But 21% unexplained variance is a signal — run a **multiple regression** with all channels (TV + radio + print) to find the optimal budget mix and identify diminishing returns at higher TV spend.

---

## 📁 Repository Structure

```
tv-advertising-sales-impact/
│
├── notebook/
│   └── simple-linear-regression-advertisment-dataset.ipynb
│
├── images/
│   ├── scatter_tv_sales.png
│   ├── regression_line.png
│   └── residual_plot.png
│
└── README.md
```

---

## 🚀 How to Run

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/tv-advertising-sales-impact.git

# Install dependencies
pip install pandas numpy statsmodels scikit-learn matplotlib seaborn

# Run the notebook
jupyter notebook notebook/simple-linear-regression-advertisment-dataset.ipynb
```

> 📎 Dataset: [Advertising CSV on Kaggle](https://www.kaggle.com/datasets/bumba5341/advertisingcsv)
