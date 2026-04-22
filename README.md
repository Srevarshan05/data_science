# Food Waste Predictor

This project contains an end-to-end Machine Learning workflow to predict food waste volumes (in kilograms) in a university canteen setting. By predicting food waste accurately, canteen operators can optimize food production, reduce financial losses, and minimize their environmental footprint.

---

## 📂 Project Structure
* **Notebook:** `food_waste_predictor.ipynb`
* **Dataset:** `food_waste.csv`
* **Outputs:** Saved model artifacts (`food_waste_model.joblib` and `feature_names.joblib`)

## 📊 Dataset Overview
The dataset consists of daily food waste records with features such as:
* **Date**: The day when the observation was recorded.
* **Meal**: Type of meal (Breakfast, Lunch, Dinner).
* **Canteen_Section**: Operational serving section (A, B, C, D).
* **Food_Category**: Classification of food (e.g., Rice, Soup, Vegetables).
* **Unit_Price_per_kg**: Price per kilogram of the food.
* **Cost_Loss**: Total financial cost of the wasted food.
* **Waste_Weight_kg**: Amount of wasted food **(Target Variable)**.

## 🚀 Methodology & Workflow
1. **Data Cleaning**: 
   * Removed duplicate entries.
   * Imputed missing numeric values using the median and missing text values using the mode.
   * Parsed dates to extract actionable temporal features (Year, Month, Day, Day of Week, IsWeekend).
2. **Exploratory Data Analysis (EDA)**: 
   * Visualized the distribution of waste and tracked average food waste trends on a monthly basis.
   * Analyzed waste variations across different meal types and food categories.
3. **Feature Engineering**: 
   * Applied One-Hot Encoding to categorical variables (`Meal`, `Canteen_Section`, `Food_Category`) to prepare them for the machine learning algorithms.
4. **Model Training & Evaluation**: 
   * Trained three distinct regression models: **Linear Regression** (with standard scaling), **Decision Tree Regressor**, and **Random Forest Regressor**.
   * Evaluated performance using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² Score.
5. **Feature Importance**: 
   * Extracted and visualized the top drivers of food waste using the Random Forest algorithm.

## 📈 Key Findings
* **Model Performance**: **Linear Regression** emerged as the best-performing model among the three tested for this dataset.
* **Primary Drivers of Waste**: Temporal features like the **Day of the month** and **Day of the week**, along with the **Meal Type** (Lunch/Dinner) and **Unit Price**, were identified as the most important factors influencing food waste amounts.

---

## ⚙️ Installation and Setup
Ensure you have Python 3.8+ installed. Run the following to install required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyterlab
```

Launch the environment and open the notebooks:
```bash
jupyter lab
```
