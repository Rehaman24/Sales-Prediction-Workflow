# CSCI 574: Final Project - Sales Forecasting

## Objective
The objective of this project is to predict weekly sales for retail stores using historical and contextual data. The analysis identifies key factors influencing sales and develops an accurate forecasting model to support strategic decision-making.


## Data Source
The datasets used for this project were sourced from [Kaggle](https://www.kaggle.com):
- **Features Dataset**:
  - Contains additional store-level metrics such as `Temperature`, `Fuel_Price`, `MarkDown1-5`, `CPI`, and `Unemployment`.
  - Includes `IsHoliday` indicator to specify holiday weeks.
- **Stores Dataset**:
  - Provides metadata about each store, including `Type` (store category) and `Size` (store area in square feet).
- **Sales Dataset**:
  - Weekly sales data for each department in the stores.
  - Includes the `Date` column to track weekly sales trends and `IsHoliday` to differentiate holiday periods.

### Data Preparation Summary
1. **Merging Datasets**:
   - The datasets were merged based on `Store` and `Date` to create a unified dataset.
2. **Handling Missing Values**:
   - Missing values in `MarkDown1-5` were imputed using mean values.
3. **Feature Engineering**:
   - Created new features for improved prediction, including interaction terms between holidays and markdowns.
4. **Scaling and Encoding**:
   - Categorical variables (`Type`) were one-hot encoded.
   - Numerical features (`CPI`, `Size`, etc.) were scaled for uniformity.

---

## Project Workflow

### 1. Data Preparation
- Merged datasets to create a unified dataset.
- Imputed missing values, encoded categorical variables, and scaled numerical features.

### 2. Exploratory Data Analysis (EDA)
- Analyzed sales trends, holiday vs. non-holiday performance, and feature correlations.

### 3. Feature Engineering and Importance Analysis
- Identified key predictors using Random Forest feature importance.

### 4. Modeling and Evaluation
- Trained and evaluated multiple regression models:
  - Linear Regression
  - Random Forest
  - Gradient Boosting
- Gradient Boosting achieved the best performance with the lowest RMSE.

### 5. Model Fine-Tuning
- Optimized Gradient Boosting hyperparameters using GridSearchCV for improved accuracy.

---

## Results
| Model              | MAE          | RMSE         |
|--------------------|--------------|--------------|
| Linear Regression  | 14,487.80    | 22,078.07    |
| Random Forest      | 14,290.99    | 21,790.57    |
| Gradient Boosting  | **14,286.27**| **21,776.40**|

- **Best Model**: Gradient Boosting Regressor
- **Key Features**:
  - `Size`: Most influential feature for predicting sales.
  - `CPI` and `Unemployment`: Significant economic indicators.

---

## Visualizations
Generated visualizations to support analysis:
1. **Feature Importance**: Highlights significant predictors of sales.
2. **PCA Visualization**: Displays clustering patterns in the data.
3. **Model RMSE Comparison**: Compares model performance.

All visualizations are saved in the `Final-Class-Figures/` directory.

---

## How to Run

### Prerequisites
- Python 3.x
- Jupyter Notebook
- Required Python libraries: `pandas`, `numpy`, `matplotlib`, `scikit-learn`

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/CSci574-Final-Project.git
   cd CSci574-Final-Project
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Sales_Forecasting_Notebook.ipynb
   ```

4. Run all cells to execute the workflow.

---

## Recommendations
1. **Focus on Large Stores**:
   - Large stores (`Size`) significantly impact sales performance.
2. **Utilize Holidays**:
   - Leverage increased sales during holidays for targeted promotions.
3. **Deploy Gradient Boosting**:
   - Use the Gradient Boosting model for forecasting future sales.

---

## Acknowledgments
This project was developed for CSci 574, using publicly available datasets from Kaggle. Special thanks to the instructor Dr .Derek Harter for guidance throughout the project.

