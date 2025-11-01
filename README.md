🏡 House Price Prediction (Regression)

My 1st ML Project!

Predicting final house sale prices using the Ames Housing dataset from Kaggle. This is an end-to-end Regression project.

🛠️ Setup

Dependencies (requirements.txt)

pip install pandas numpy scikit-learn matplotlib seaborn


File Structure

House_Price_Prediction/
├── data/
│   ├── train.csv         
│   └── test.csv          
├── house_price_model.ipynb 
└── requirements.txt      


📅 Day 1 Log: Data Cleaning Summary

Goal: Clean and unify the 79 features for modeling.

Step

Action

Method & Result

1. Unification

Loaded data and separated SalePrice (Y_train).

Concatenated 79 features into a single all_data DataFrame (2,919 rows).

2. Analysis

Checked $\text{NaN}$ values (missing data).

Confirmed missing data (e.g., $99\%$ in PoolQC) means "No Feature".

3. Imputation

Filled all $\text{NaN}$s.

1. Categorical: Filled PoolQC, GarageType, etc., with 'None' string. 2. Numerical: Filled GarageArea, TotalBsmtSF with $0$. 3. Statistical: Used Median by Neighborhood for LotFrontage.

Result: The all_data DataFrame is now $100\%$ clean and ready for numerical conversion.

➡️ Next Steps (Day 2 Focus)

Transform Y: Apply $\text{log}$ to Y_train (SalePrice).

Encode X: Use One-Hot Encoding to convert categorical strings (like 'RL', 'None') to numbers.

Model: Train baseline Linear Regression.