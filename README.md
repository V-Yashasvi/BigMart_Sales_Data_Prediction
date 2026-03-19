# Big Mart Sales Prediction

This project aims to build a predictive model using **XGBoost Regressor** to determine the sales of various products at different Big Mart outlets. By analyzing factors such as item weight, fat content, and outlet size, the model helps the business understand the properties of products and stores that play a crucial role in increasing sales.

## Dataset

The dataset consists of 8,523 rows and 12 features. It includes:

  * **Item Details:** Identifier, Weight, Fat Content, Visibility, Type, and MRP.
  * **Outlet Details:** Identifier, Establishment Year, Size, Location Type, and Type.
  * **Target Variable:** Item_Outlet_Sales.

-----

## Project Workflow

1.  **Data Collection:** Loading the [Big Mart Train dataset](https://www.kaggle.com/datasets/brijbhushannanda1979/bigmart-sales-data?resource=download).
2.  **Data Cleaning:**  Imputed missing values for `Item_Weight` using the **Mean**.
      * Imputed missing values for `Outlet_Size` using the **Mode** based on `Outlet_Type`.
3.  **Data Analysis (EDA):** Visualizing numerical and categorical features using `sns.displot()` and `sns.countplot()`.
4.  **Data Pre-processing:**  Standardizing labels in `Item_Fat_Content` (e.g., mapping 'LF' and 'low fat' to 'Low Fat').
      * **Label Encoding** categorical variables into numerical values.
5.  **Train-Test Split:** Dividing data (80/20) with a fixed `random_state=2` for reproducibility.
6.  **Model Training:** Training an **XGBoost Regressor** model.
7.  **Evaluation:** Measuring performance using the **R-Squared** metric.

-----

## Technologies Used

  * **Language:** Python
  * **Libraries:**  **Pandas & NumPy:** Data manipulation.
      * **Matplotlib & Seaborn:** Data visualization.
      * **Scikit-learn:** Data splitting and evaluation.
      * **XGBoost:** Gradient boosted decision trees for regression.

-----

## Exploratory Data Analysis

Key insights from the EDA:

  * **Item\_MRP:** The distribution shows four distinct price ranges.
  * **Outlet\_Establishment\_Year:** The count plot reveals that most outlets in the dataset were established in 1985, while 1998 has the lowest representation.
  * **Item\_Outlet\_Sales:** The sales data is right-skewed, indicating that a majority of items have lower sales values, with a few high-value exceptions.

-----

## Model Performance

The model was evaluated using the R-Squared ($R^2$) value:

  * **Training Data $R^2$ Score:** \~0.877
  * **Test Data $R^2$ Score:** \~0.512

> **Note:** The gap between training and test scores suggests potential overfitting, which can be improved through hyperparameter tuning.

## How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/V-Yashasvi/BigMart_Sales_Data_Prediction
cd big-mart-sales-prediction
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn xgboost scikit-learn
```

### 3. Run the Project

  * **Via Jupyter Notebook:**
    Open `BigMart_Sales_Data_Prediction.ipynb` in Jupyter or [Google Colab](https://www.google.com/search?q=https://colab.research.google.com/drive/1VG5nKZiKLNTWEJtVrdcW25hffldwZ9Tw).
  * **Via Python Script:**
    Run the script directly in your terminal:
    ```bash
    python predict_sales.py
    ```
