# 🏡 House Price Prediction (Regression)

## My First ML Project! (Started: Nov 1, 2025)

Predicting final house sale prices using the Ames Housing dataset from Kaggle. This is a classic **Regression** challenge.

## 🛠️ Setup

### Dependencies (`requirements.txt`)
pandas numpy scikit-learn matplotlib seaborn

### File Structure
House_Price_Prediction/ ├── data/ │ ├── train.csv

│ └── test.csv

├── house_price_model.ipynb └── requirements.txt

## 📅 Day 1 Log: Data Cleaning (Code Documentation)

### **Goal:** Achieve a $100\%$ clean feature set (X) for modeling.

| Step | Action | Python Code Snippet | 
| :--- | :--- | :--- | 
| **1. Unification** | Combine train/test features; separate `Y_train`. | `Y_train = train_data['SalePrice']` | 
|  |  | `all_data = pd.concat([train_data, test_data], ignore_index=True)` | 
| **2. Categorical NaNs** | Fill high-missing categorical features (Pool, Garage, Bsmt, etc.) with the string `'None'`. | `all_data[col].fillna('None')` | 
| **3. Numerical Zeros** | Fill area/count features (e.g., Garage Area, Basement SF) with the number $0$. | `all_data[col].fillna(0)` | 
| **4. Statistical Imputation** | Fill remaining low-count numerical features using median grouped by neighborhood. | `all_data.groupby('Neighborhood')['LotFrontage'].transform(lambda x: x.fillna(x.median()))` | 

**Result:** `all_data` is now completely clean and ready for numerical feature transformation.

## ➡️ Next Steps (Day 2 Focus)

1. **Transform Y:** Apply $\text{log}$ transformation to the target variable (`Y_train`).

2. **Encode X:** Use **One-Hot Encoding** to convert all strings to numerical features.

3. **Model:** Train baseline **Linear Regression**.

