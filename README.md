# 📊 Walmart Sales Forecasting using SARIMAX

## 📌 Project Overview

This project focuses on analyzing and forecasting **weekly sales data from Walmart stores** using **time series analysis** and the **SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous variables)** model.

The project performs store-level sales analysis, identifies seasonal patterns and trends, compares sales across different stores, and generates future sales forecasts.

---

## 🎯 Objectives

* Analyze weekly sales data for individual Walmart stores.
* Visualize sales trends over time.
* Identify seasonal patterns using time series decomposition.
* Compare the sales performance of different stores.
* Build a SARIMAX time series forecasting model.
* Generate one-step-ahead and dynamic forecasts.
* Evaluate forecasting performance using:

  * Mean Squared Error (MSE)
  * Root Mean Squared Error (RMSE)
* Forecast future weekly sales.

---

## 📂 Dataset

The project uses the **Walmart Sales Dataset**, which contains weekly sales information for multiple Walmart stores.

The dataset includes information such as:

* Store ID
* Date
* Weekly Sales

The dataset contains approximately **45 different stores**, allowing store-level analysis and comparison.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Statsmodels
* Google Colab

---

## 📊 Project Workflow

### 1. Data Loading

The Walmart dataset is loaded using Pandas.

```python
data1 = pd.read_csv('Walmart DataSet.csv')
```

The `Date` column is used as the index for time series analysis.

---

### 2. Store Selection

The user can select a specific Walmart store for analysis.

```python
a = int(input("Enter the store id:"))
store = data1[data1.Store == a]
```

The weekly sales for the selected store are then aggregated by date.

---

### 3. Sales Trend Visualization

The project visualizes weekly sales over time to understand the overall sales behavior of a store.

This helps identify:

* Sales trends
* Fluctuations
* Seasonal patterns
* Possible irregularities

---

### 4. Seasonal Decomposition

The time series is decomposed using:

```python
seasonal_decompose()
```

This separates the sales data into:

* Trend
* Seasonality
* Residuals

The decomposition helps better understand the underlying structure of the sales data.

---

### 5. Store Comparison

The project also compares the sales performance of different Walmart stores.

For example, weekly sales from two stores can be plotted together to analyze differences in their sales patterns.

---

## 🤖 SARIMAX Model

The project uses the **SARIMAX model** for forecasting weekly sales.

The model configuration used is:

```python
SARIMAX(
    y1,
    order=(4, 4, 3),
    seasonal_order=(1, 1, 0, 52),
    enforce_invertibility=False
)
```

The seasonal period of **52** represents approximately one year of weekly sales data.

---

## 📈 Forecasting

The project generates two types of forecasts:

### One-Step Ahead Forecast

Predictions are generated using known observations from the dataset.

This allows the model's predicted values to be compared against actual sales.

### Dynamic Forecast

Dynamic forecasting predicts future values by using previous predictions rather than continuously relying on actual observations.

---

## 📏 Model Evaluation

The forecasting model is evaluated using the following metrics.

### Mean Squared Error (MSE)

```python
mse = ((y_forecasted - y_truth) ** 2).mean()
```

### Root Mean Squared Error (RMSE)

```python
rmse = np.sqrt(((y_forecasted - y_truth) ** 2).mean())
```

These metrics measure the difference between predicted weekly sales and actual weekly sales.

The project also calculates the absolute residual error between the forecasted and actual values.

---

## 🔮 Future Forecasting

After training the SARIMAX model, future sales are forecasted using:

```python
pred_uc = results.get_forecast(steps=12)
```

This generates predictions for the next **12 time periods**.

---

## 📁 Project Structure

```text
Walmart-Sales-Forecasting/
│
├── WalmartCapstone.ipynb
├── Walmart DataSet.csv
├── README.md
└── requirements.txt
```

---

## ⚙️ Installation and Usage

### 1. Clone the Repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the Project Directory

```bash
cd Walmart-Sales-Forecasting
```

### 3. Install Dependencies

```bash
pip install numpy pandas matplotlib seaborn statsmodels
```

### 4. Run the Notebook

Open the Jupyter Notebook:

```bash
jupyter notebook WalmartCapstone.ipynb
```

Alternatively, upload the notebook to **Google Colab**.

Make sure the Walmart dataset path is correctly configured before running the notebook.

---

## 📌 Key Concepts Used

* Time Series Analysis
* Seasonal Decomposition
* Sales Trend Analysis
* Store-Level Analysis
* SARIMAX
* One-Step Ahead Forecasting
* Dynamic Forecasting
* Mean Squared Error
* Root Mean Squared Error
* Residual Analysis

---

## 🚀 Future Improvements

Some potential improvements for this project include:

* Automatically selecting optimal SARIMA/SARIMAX parameters.
* Using exogenous variables such as:

  * Temperature
  * Fuel Price
  * CPI
  * Unemployment Rate
  * Holiday Information
* Comparing SARIMAX with machine learning models.
* Building an interactive dashboard for sales forecasting.
* Deploying the model as a web application.
* Automating sales forecasts for all Walmart stores.

---

## 👨‍💻 Author

**Ash**

Computer Science Undergraduate
Shiv Nadar University Chennai

---

⭐ If you found this project interesting, consider giving the repository a star!
