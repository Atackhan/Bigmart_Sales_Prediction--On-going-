Tabii! İşte projen için detaylı bir **README.md** dosyası:

---

# **BigMart Sales Prediction**

This project aims to analyze and predict sales for different outlets in the BigMart dataset using machine learning techniques.

## **Table of Contents**
- [Introduction](#introduction)
- [Dataset Description](#dataset-description)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Model Building](#model-building)
- [Hyperparameter Tuning](#hyperparameter-tuning)
- [Results & Insights](#results--insights)

---

## **Introduction**
BigMart is a retail chain that operates multiple outlets across different locations. This project focuses on analyzing various factors that influence sales and building a predictive model to forecast sales based on historical data.

The goal is to leverage **machine learning algorithms** to identify key patterns and optimize sales strategies.

---

## **Dataset Description**
The dataset consists of **8523** records with **12 columns**, including:
- `Item_Identifier`: Unique product ID
- `Item_Weight`: Weight of the item (some missing values)
- `Item_Fat_Content`: Fat content (Low Fat / Regular)
- `Item_Visibility`: How prominently an item is displayed
- `Item_Type`: Category of the item
- `Item_MRP`: Maximum Retail Price (MRP)
- `Outlet_Identifier`: Unique store ID
- `Outlet_Establishment_Year`: Year when the store was established
- `Outlet_Size`: Store size (Small, Medium, High)
- `Outlet_Location_Type`: Store location category (Tier 1, Tier 2, Tier 3)
- `Outlet_Type`: Type of store (Supermarket, Grocery Store, etc.)
- `Item_Outlet_Sales`: **Target variable** - sales revenue for each item-store combination

---

## **Data Preprocessing**
To ensure high-quality data, we performed:
✅ **Handling Missing Values**:
- `Item_Weight`: Filled missing values using **median imputation**.
- `Outlet_Size`: Used **KNN Imputer** to predict missing values.

✅ **Encoding Categorical Data**:
- Applied **Label Encoding** to convert categorical values into numeric format.

✅ **Feature Scaling**:
- Used **MinMaxScaler** to normalize numerical features for better model performance.

✅ **Feature Selection**:
- Removed columns like `Item_Identifier` that do not contribute to prediction.

---

## **Exploratory Data Analysis (EDA)**
We performed various analyses to understand the sales patterns:
📊 **Total Sales Across Locations**:
- Created **bar plots** to visualize sales in different locations.

📊 **Sales Trends Over Years**:
- **Box plots** showed that stores established in **1985** performed the best.
- Stores from **1998** had significantly lower performance.

📊 **Impact of Product Pricing (MRP) on Sales**:
- Found a **positive correlation** between product price (MRP) and sales.

📊 **Impact of Product Visibility on Sales**:
- No strong correlation between visibility and sales, suggesting other factors (branding, promotions) have a greater influence.

📊 **Correlation Matrix**:
- Built a **heatmap** to identify relationships between different features.

---

## **Feature Engineering**
🔹 **Created new features** based on existing ones:
- Extracted **years of operation** from `Outlet_Establishment_Year`.
- Grouped similar categories in `Item_Fat_Content`.

🔹 **Removed unnecessary identifiers**:
- Dropped `Item_Identifier` as it doesn’t contribute to sales prediction.

---

## **Model Building**
We trained various **machine learning models** for predicting `Item_Outlet_Sales`:

✔ **Linear Regression**  
✔ **Lasso Regression**  
✔ **Decision Tree Regressor**  
✔ **Random Forest Regressor**  
✔ **LightGBM Regressor**  
✔ **XGBoost Regressor**  

Each model was trained using **cross-validation** to ensure robustness.

---

## **Hyperparameter Tuning**
We used **RandomizedSearchCV** to optimize hyperparameters for:
1. **Random Forest Regressor**  
   - Tuned parameters: `max_depth`, `min_samples_split`, `min_samples_leaf`, `max_features`
2. **LightGBM Regressor**  
   - Tuned parameters: `learning_rate`, `max_depth`, `n_estimators`, `subsample`

---

## **Results & Insights**
📌 **Key Takeaways**:
- Established stores (especially from **1985**) tend to have higher sales.
- **Item MRP** strongly correlates with sales, while **Item Visibility** does not.
- **LightGBM and XGBoost** outperformed other models in terms of accuracy.

---

## **Installation & Usage**
To run this project locally, follow these steps:

### **1. Clone the repository**
```bash
git clone https://github.com/your-username/BigMart-Sales-Prediction.git
cd BigMart-Sales-Prediction
```

### **2. Install dependencies**
```bash
pip install -r requirements.txt
```

### **3. Run the Jupyter Notebook**
```bash
jupyter notebook
```

Open the notebook and run the code cells step by step.

---
