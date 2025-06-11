# 🏡 Data Houses: Kaggle Competition

A repository for exploring and modeling the "House Prices: Advanced Regression Techniques" competition from Kaggle. Learn to engineer features, compare regression models, and refine predictions for Ames, Iowa housing data.

---

## 📌 Overview

- **Objective**: Predict house sale prices using ~80 features for 1,460 houses.  
- **Dataset**: Includes `train.csv` (with prices) and `test.csv` (without prices). Target evaluation metric: **RMSLE**.  
- Practice **EDA**, **feature engineering**, **model comparison**, and **hyperparameter tuning** (linear models, RFs, XGBoost, ensembles).

---

## 📂 Repository Structure

```
.
├── data/                 # Kaggle-provided CSVs and feature descriptions
├── notebooks/           # EDA, modeling, and tuning notebooks
├── src/                 # Python modules (data prep, modeling, utils)
├── models/              # Saved model artifacts and predictions
├── submissions/         # CSVs for Kaggle submission
└── README.md
```

---

## 🎯 Getting Started

### 1. Download the Dataset

Sign in to [Kaggle – House Prices](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) and download:
- `train.csv`
- `test.csv`
- `data_description.txt`

Place them in the `data/` folder.

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

Key libraries:
- `pandas`, `numpy`, `scikit-learn`
- `xgboost`, `matplotlib`, `seaborn`
- `joblib` for model persistence

---

## 🧪 Workflow

### 1. Exploratory Data Analysis & Feature Engineering
- Visualize distributions (SalePrice, correlations, scatter/box plots)  
- Log-transform skewed features/target  
- Fill missing values (e.g., median for LotFrontage)  
- Create new features (age, total areas, boolean flags)  

### 2. Preprocessing Pipeline
- Combine train+test for consistent encoding  
- One-hot encode categorical variables  
- Scale numeric features  
- Split back into train/test sets

### 3. Model Training & Evaluation
- Baselines: Linear Regression, Ridge, Lasso  
- Tree models: RandomForest, XGBoost, ExtraTrees  
- Evaluate using cross-validated RMSLE  
- Hyperparameter tuning via `GridSearchCV`  

### 4. Ensemble Approaches
- Stack Ridge, Lasso, GBM as meta-features for XGBoost  

### 5. Submit & Improve
- Save predictions to `submissions/`
- Generate submission CSVs with `SalePrice`
- Track leaderboard performance (~0.14 RMSLE is competitive)

---

## 📈 Results & Benchmarks

| Model                    | CV RMSLE | Kaggle Score |
|-------------------------|----------|--------------|
| Baseline (no tuning)    | ~1.139   | 0.1427       |
| Tuned XGBoost           | ~1.138   | 0.1365       |
| Ensemble (Stacking)     | —        | *Try to improve further!* |

---

## 💡 Tips & Further Improvements

- **Log-transform target/features** improves linear model fit  
- **Train/test alignment**: one-hot encoding requires combined fit  
- **Feature engineering** matters: Age, Renovation, Quality columns are strong predictors  
- **Regularization & ensembles** help reduce overfitting  
- **Ensembling methods**: stacking multiple models tends to boost performance  

---

## 🚀 Next Steps

- Add **cross-validation scripts** and reproducible pipelines  
- Integrate **LightGBM, CatBoost**  
- Build **Shap/feature importance plots** and model interpretability  
- Deploy model via **Flask/FastAPI** or build a simple **web demo**

---

## 📚 References & Further Reading

- Kaggle competition overview and dataset  
- Data analysis guides from NYC Data Science, Medium  
- Top solutions via Reddit and GitHub posts  

---

## 📄 License

Licensed under MIT © Saran Jaya Thilak 2025
