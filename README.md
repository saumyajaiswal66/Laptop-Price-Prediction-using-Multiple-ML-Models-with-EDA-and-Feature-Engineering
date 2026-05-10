# 💻 Laptop Price Predictor

A machine learning project that predicts laptop prices based on hardware specifications
like CPU, RAM, GPU, Storage, and Display features.
Built using Python and Scikit-learn with an R² score of **88.5%** on the test set.

---

## 📌 Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Key Findings](#key-findings)
- [Model Results](#model-results)
- [Technologies Used](#technologies-used)
- [How to Run](#how-to-run)
- [Future Scope](#future-scope)

---

## 📖 Project Overview

Buying a laptop can be confusing — why does one laptop cost ₹40,000 and another
₹1,40,000 with seemingly similar specs? This project answers that question using
data and machine learning.

We trained a **Random Forest Regressor** on 1300+ real laptop listings to predict
price from specs — and identified which features drive price the most.

---

## 📂 Dataset

- **Source** : [Kaggle - Laptop Price Dataset](https://www.kaggle.com/datasets/ionaskel/laptop-prices)
- **Size** : 1303 rows × 12 columns (after removing 29 duplicates → 1274 rows)
- **Features** : Company, TypeName, Inches, ScreenResolution, CPU, RAM,
  Memory, GPU, OpSys, Weight, Price

---

## 🔄 Project Workflow

### 1. Data Cleaning
- Removed 29 duplicate rows
- Extracted numeric values from `RAM` (e.g. `8GB → 8`) and `Weight` (e.g. `1.5kg → 1.5`)
- Verified no null values exist in the dataset

### 2. Feature Engineering
This is the most important part of the project. Raw columns had messy text data
that needed to be converted into meaningful numeric features.

| Original Column | What We Did | New Feature(s) |
|---|---|---|
| ScreenResolution | Extracted touch/IPS flags, computed pixel density | `TouchScreen`, `IPS`, `PPI` |
| CPU | Categorized into i3 / i5 / i7 / Other Intel / AMD | `CPU_Name` |
| Memory | Parsed HDD and SSD storage values separately | `HDD`, `SSD` |
| GPU | Extracted brand (Nvidia / Intel / AMD) | `Gpu_brand` |
| OpSys | Grouped into Windows / Mac / Other | `OpSys` |

**Notable engineering decision** : Instead of keeping X-Resolution, Y-Resolution,
and Screen Size as 3 separate columns, we combined them into a single
`PPI (Pixels Per Inch)` feature — which had better correlation with Price
and reduced multicollinearity.

### 3. Exploratory Data Analysis
- Distribution analysis of Price (identified right skew → applied log transformation)
- Brand-wise, CPU-wise, GPU-wise price comparisons
- Correlation heatmap of all numeric features
- Touchscreen vs Non-touchscreen price comparison
- IPS vs Non-IPS price comparison

### 4. Model Building
- Applied `np.log()` on Price to handle skewed distribution
- Used **Scikit-learn Pipelines** with `ColumnTransformer` for clean preprocessing
- Trained and compared 5 regression models

---

## 💡 Key Findings

1. **SSD is the strongest price predictor** — SSD laptops cost significantly
   more than HDD laptops with similar specs
2. **RAM directly drives price** — 16GB+ RAM laptops are nearly 2x more
   expensive than 4/8GB variants
3. **CPU type matters** — Intel i7 > i5 > i3 > AMD in terms of average price
4. **Touchscreen adds a price premium** of roughly 20-30% on average
5. **IPS panels increase price** due to better display quality
6. **Mac OS laptops are the most expensive** on average across all brands
7. **Nvidia GPU laptops cost more** — driven by gaming and creative workloads
8. **Higher PPI = Higher Price** — premium displays command a premium price

---

## 📊 Model Results

| Model | R² Score | MAE |
|---|---|---|
| 🏆 Random Forest | **0.8851** | **0.1587** |
| Decision Tree | 0.8376 | 0.1843 |
| Ridge Regression | 0.8127 | 0.2093 |
| Linear Regression | 0.8073 | 0.2102 |
| Lasso Regression | 0.8071 | 0.2111 |

**Random Forest Regressor** performed best with **R² = 0.885**, meaning the model
explains 88.5% of the variation in laptop prices.

> Note : Price was log-transformed before training. MAE values are in log scale.

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Pandas | Data manipulation and cleaning |
| NumPy | Numerical operations |
| Matplotlib & Seaborn | Data visualization |
| Scikit-learn | ML models, pipelines, preprocessing |
| Pickle | Model serialization |
| Jupyter Notebook | Development environment |

---

## ▶️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/saumyajaiswal66/laptop-price-predictor.git
cd laptop-price-predictor
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3. Run the notebook
```bash
jupyter notebook laptop_price_prediction.ipynb
```

> Make sure `laptop_data.csv` is in the same folder as the notebook before running.

---

## 🚀 Future Scope

- [ ] Deploy as a live web app using **Streamlit**
- [ ] Add 2023–2025 laptop data for updated predictions
- [ ] Try **XGBoost / LightGBM** for better accuracy
- [ ] Add feature importance visualization
- [ ] Build a price comparison tool (user inputs specs → see where it falls
      in the market)

---

## 👤 Author

**Saumya Jaiswal**
- GitHub : [@saumyajaiswal66](https://github.com/saumyajaiswal66)

---

⭐ If you found this project helpful, please consider giving it a star on GitHub!
