# Nebraska K–12 Chronic Absenteeism — ML Analysis

**Author:** Abhinav Adhikari  
**Course:** DSCI 8950 — Data Science Capstone  
**Institution:** University of Nebraska Omaha  

---

## 📓 View the Notebook

**[Launch on nbviewer →](https://nbviewer.org/github/abhadhikariuno/SP_2026_Team-B/blob/main/Nebraska_ML_Notebook_v1.ipynb)**

---

## Project Overview

This project applies machine learning to predict district-level chronic absenteeism rates across Nebraska public schools using 7 years of NDE data (2018–19 through 2024–25).

**Research question:** Can we predict which Nebraska school districts will have high chronic absenteeism, and what are the strongest drivers?

**ML models used:**
- Decision Tree Regressor (baseline, interpretable)
- XGBoost (tuned, best performance)

**Key findings:**
- XGBoost (tuned) achieves **RMSE ≈ 2.0pp** and **R² ≈ 0.92** on the held-out test set
- FRL% (poverty proxy) is the strongest advance-available predictor
- The 15-day absence threshold is the best mid-year early warning signal
- Post-COVID recovery is visible — captured by the year feature

---

## Dataset

All data is sourced from the **Nebraska Department of Education (NDE)** — publicly available, no login required.

| Year | Absence File | FRL File | Source |
|------|-------------|----------|--------|
| 2018-19 | absence_2018-19.xlsx | frl_2018-19.xls | [NDE Archive](https://www.education.ne.gov/dataservices/data-reports/data-and-information-archives/) |
| 2019-20 | absence_2019-20.xlsx | frl_2019-20.xls | [NDE Archive](https://www.education.ne.gov/dataservices/data-reports/data-and-information-archives/) |
| 2020-21 | absence_2020-21.xlsx | frl_2020-21.xls | [NDE Archive](https://www.education.ne.gov/dataservices/data-reports/data-and-information-archives/) |
| 2021-22 | absence_2021-22.xlsx | frl_2021-22.xlsx | [NDE Data Reports](https://www.education.ne.gov/dataservices/data-reports/) |
| 2022-23 | absence_2022-23.xlsx | frl_2022-23.xlsx | [NDE Data Reports](https://www.education.ne.gov/dataservices/data-reports/) |
| 2023-24 | absence_2023-24.xlsx | frl_2023-24.xlsx | [NDE Data Reports](https://www.education.ne.gov/dataservices/data-reports/) |
| 2024-25 | absence_2024-25.xlsx | frl_2024-25.xlsx | [NDE Data Reports](https://www.education.ne.gov/dataservices/data-reports/) |

---

## Repo Structure

```
SP_2026_Team-B/
├── data/
│   ├── absence_2018-19.xlsx
│   ├── absence_2019-20.xlsx
│   ├── absence_2020-21.xlsx
│   ├── absence_2021-22.xlsx
│   ├── absence_2022-23.xlsx
│   ├── absence_2023-24.xlsx
│   ├── absence_2024-25.xlsx
│   ├── frl_2018-19.xls
│   ├── frl_2019-20.xls
│   ├── frl_2020-21.xls
│   ├── frl_2021-22.xlsx
│   ├── frl_2022-23.xlsx
│   ├── frl_2023-24.xlsx
│   └── frl_2024-25.xlsx
├── Nebraska_ML_Notebook.ipynb
└── README.md
```

---

## Running Locally

```bash
git clone https://github.com/abhadhikariuno/SP_2026_Team-B.git
cd SP_2026_Team-B

pip install pandas numpy matplotlib seaborn scikit-learn xgboost scipy openpyxl xlrd jupyter

jupyter notebook Nebraska_ML_Notebook.ipynb
```

Python 3.9+ required. The notebook auto-detects the `data/` folder — no path changes needed.

---

## Notebook Structure

| Section | Description |
|---------|-------------|
| 1 | Imports |
| 2 | Load & build 7-year panel dataset |
| 3 | Feature engineering |
| 4 | Exploratory analysis |
| 5 | Decision Tree — default (overfitting diagnosis) |
| 6 | Decision Tree — depth sweep |
| 7 | Decision Tree — GridSearchCV tuning |
| 8 | Decision Tree — visualise rules |
| 9 | XGBoost — default baseline |
| 10 | XGBoost — learning curves |
| 11 | XGBoost — GridSearchCV tuning |
| 12 | Side-by-side comparison |
| 13 | Predicted vs actual |
| 14 | Feature importance |
| 15 | Residual analysis |
| 16 | Per-year generalization check |
| 17 | Final summary |

---

## Dependencies

```
pandas / numpy / matplotlib / seaborn
scikit-learn / xgboost / scipy
openpyxl / xlrd / jupyter
```
