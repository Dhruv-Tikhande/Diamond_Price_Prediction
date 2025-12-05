# 💎 Diamond Price Prediction – Machine Learning Project

A complete end-to-end Machine Learning pipeline built to predict the price of diamonds based on their physical and categorical attributes.  
This project demonstrates **data cleaning, encoding, feature engineering, model building, evaluation, and exporting a trained model**, making it suitable for real-world ML applications.

---

## 📌 **Project Overview**

The goal of this project is to build a regression model that accurately predicts the price of a diamond using features like:
- Carat  
- Cut  
- Color  
- Clarity  
- Depth  
- Table  
- Dimensions (x, y, z)

This is a widely used dataset in ML education and is great for learning **feature engineering, preprocessing, and model comparison**.

---

## 📂 **Dataset Information**

**Dataset:** diamonds.csv  
**Rows after cleaning:** ~53,676  
**Target variable:** `price`  
**Feature types:**
- Numerical: carat, depth, table, x, y, z  
- Categorical (ordinal): cut, color, clarity  

---

## 🧹 **Data Cleaning & Preprocessing**

### ✔ Removed invalid rows  
Rows where `x = 0`, `y = 0`, or `z = 0` were removed — these are physically impossible dimensions.

### ✔ Ordinal Encoding  
Applied domain-correct encoding:

#### **Cut (Quality Order)**  
Fair → Good → Very Good → Premium → Ideal  
```
Fair:1, Good:2, Very Good:3, Premium:4, Ideal:5
```

#### **Color (Best → Worst)**  
D → E → F → G → H → I → J  
```
J:1 … D:7
```

#### **Clarity (Worst → Best)**
I1 → SI2 → SI1 → VS2 → VS1 → VVS2 → VVS1 → IF  
```
I1:1 … IF:8
```

### ✔ Domain-based Outlier Removal  
Professional gemology ranges were used:
- Depth: **56–70**  
- Table: **53–66**  
- x, y: **> 0 and < 10**  
- z: **> 0 and < 7**

---

## 🔧 **Models Used**

Two primary models were trained:

### **1️⃣ Linear Regression (Baseline)**
- R²: **0.91**  
- MAE: ~790  
- RMSE: ~1183  

### **2️⃣ Random Forest Regressor (Final Model)**
Using tuned hyperparameters:
```python
{'n_estimators': 150, 'max_depth': None, 'min_samples_split': 5}
```

📌 **Performance:**  
- **R²: 0.981**  
- **MAE: 266**  
- **RMSE: 547**  

This shows the Random Forest model is extremely accurate and stable.

---

## 📊 **Visualizations Included**

The project generates the following plots:
- Feature Importance Bar Plot  
- Residual Error Distribution  
- Actual vs Predicted Price Scatter Plot  
- Correlation Heatmap  
- Price vs Carat graph  

All plots are saved inside `/images`.

---

## 🧠 **Feature Importance (Top Drivers of Price)**

Highest impact features:
1. **Carat**
2. **Y dimension**
3. **Clarity**
4. **Color**
5. **X dimension**

This matches real-world gem pricing logic.

---

## 📦 **Files Included**

| File | Description |
|------|-------------|
| `diamond_price_pipeline.py` | Full end-to-end ML script |
| `diamond_price_model.pkl` | Saved trained Random Forest model |
| `notebook.ipynb` | Jupyter Notebook version of the project |
| `model_summary.csv` | Model evaluation summary |
| `/images/*` | Saved visualizations |
| `README.md` | Project documentation |

---

## 🚀 **How to Run the Project**

### Install dependencies:
```
pip install -r requirements.txt
```

### Run the ML pipeline:
```
python diamond_price_pipeline.py
```

### Run prediction on sample input:
```
python load_model_demo.py
```

---

## 🌐 **Future Improvements**
- Deploy using **Streamlit**  
- Add **XGBoost and Gradient Boosting** models  
- Hyperparameter tuning using **Optuna**  
- Build a small web app to predict diamond prices interactively  

---

## 👤 **Author**
**Dhruv Tukaram Tikhande**  
B.E. Information Technology  
Portfolio: *add your link here*  
GitHub: *add your link here*

---

## ⭐ **Why This Project is Strong for ML Resume**
- Shows complete ML pipeline knowledge  
- Includes both ML theory + practical implementation  
- Domain-driven cleaning + feature engineering  
- Model comparison included  
- Strong visualization support  
- Exported model ready for deployment  

---

If you like this project, feel free to ⭐ the repo!
