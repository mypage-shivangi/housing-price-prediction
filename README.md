# 🏠 House Price Prediction – Regression Model

This project uses machine learning to predict house sale prices using the Ames Housing Dataset. The goal is to build a robust regression model that generalizes well — a classic Kaggle regression task.

---

## 📌 Problem Statement

**Goal:** Predict the sale price of residential homes based on housing features like quality, area, year built, etc.

**Dataset Source:** [Kaggle House Prices - Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)

---

## 🔍 Data Exploration & Preprocessing

- **Missing Value Handling:**
  - Added missingness indicators (e.g., `missing_FireplaceQu`, `missing_Alley`)
  - Imputed categorical variables with `'None'`, numerical with median
- **Feature Engineering:**
  - `TotalArea` = `GrLivArea` + `TotalBsmtSF`
  - `AgeOfHouse` = `YrSold` - `YearBuilt`
  - `YearsSinceRemod` = `YrSold` - `YearRemodAdd`
  - `TotalBath` = `FullBath` + 0.5 × `HalfBath`
  - `IsRemodeled`: Binary indicator for remodel
  - `HasPorch`: Indicates any type of porch present
  - Composite scores for `GarageScore` and `BasementScore` based on quality indicators
- **Feature Selection:**
  - Top 20 features selected using Pearson correlation with `SalePrice`

---

## ⚙️ Modeling Approach

We experimented with multiple models to find the best-performing regression algorithm.

### 🔢 Models Benchmark

| Model              | RMSE     | R² Score | Cross-Validated RMSE |
|-------------------|----------|----------|-----------------------|
| **Random Forest**      | 0.1553   | 0.8708   | 0.1519                |
| **Gradient Boosting**  | **0.1548** | **0.8716** | **0.1471**             |
| **XGBoost**            | 0.1571   | 0.8678   | 0.1467                |
| **ElasticNet**         | 0.3815   | 0.8102   | 0.3720                |

---

## ✅ Submission & Performance

- Log-transformed target variable for regression (`np.log1p(SalePrice)`)
- Submission file created using predictions from the **Gradient Boosting model**
- Final public leaderboard score: **0.23**
- Rank: **~4000**

---

## 📌 Key Learnings

- Feature engineering improves performance more than model complexity alone.
- Handling missing values with domain knowledge leads to more meaningful features.
- Simpler models like ElasticNet underperformed compared to tree-based methods.

---

## 🛠 Future Improvements

- Use stacking or blending to ensemble multiple models
- SHAP values for model interpretability
- Add Streamlit app for interactive predictions

---

## 📁 Files

- `House Prices Advanced Regresion Techniques.ipynb` → https://www.kaggle.com/code/shivangi2k18/house-prices-advanced-regresion-techniques
- `data/` → https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data
- `submission.csv` → https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/submissions

---

## 📬 Contact

If you'd like to collaborate, reach out on LinkedIn : https://www.linkedin.com/in/shivangigupta01/


