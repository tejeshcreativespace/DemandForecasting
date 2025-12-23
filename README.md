
# Store Item Demand Forecasting

I built this machine learning project to predict retail sales demand for the next 3 months. I followed a tutorial to learn the concepts and then implemented everything myself to understand how demand forecasting works in real-world retail scenarios.

## What This Project Does

This predicts how many units of each item will sell at each store location over the next 90 days. Retailers can use these forecasts to optimize inventory, avoid stockouts, and reduce waste from overstocking.

## The Dataset

I worked with the Kaggle Store Item Demand Forecasting Challenge dataset:
- 5 years of daily sales data (2013-2017)
- 10 different stores
- 50 unique items per store
- About 913,000 sales records total

The goal was to predict future sales for each store-item combination.

## What I Did

### 1. Data Exploration
First, I loaded the data and explored it to understand patterns:
- Looked at sales trends over time
- Checked how different stores and items perform
- Identified seasonal patterns and trends
- Visualized the data using matplotlib and seaborn

### 2. Feature Engineering
This was the most important part. I created features that capture patterns in the sales data:

- **Date features**: Extracted year, month, day, day of week from dates
- **Lag features**: Created variables showing sales from 91, 98, 105, 112, 119, 126, 182, and 364 days ago (these turned out to be really important)
- **Rolling averages**: Calculated moving averages over different time windows
- **Seasonal indicators**: Added weekend flags and holiday markers
- **Cyclical encoding**: Used sine/cosine transformations for monthly patterns

### 3. Model Building
I trained and compared three different models:

- **Linear Regression** - Started with this as a baseline
- **Random Forest** - Used this to capture non-linear relationships
- **XGBoost** - This gave me the best results

For each model, I experimented with hyperparameters to improve performance.

### 4. Evaluation
I measured performance using:
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)  
- R² Score

The XGBoost model performed best with an RMSE around 17,000 and R² of 0.99. This was about 32% better than just using a rolling mean.

## Tech Stack

- **Python 3**
- **pandas** and **numpy** for data manipulation
- **scikit-learn** for preprocessing and models
- **XGBoost** for gradient boosting
- **matplotlib** and **seaborn** for visualizations
- **Jupyter Notebook** for development

## Key Findings

- Lag features (especially 91-day and 182-day lags) were the most predictive
- There are clear seasonal patterns - some items sell better on weekends, others on weekdays
- Store location matters - different stores have different demand patterns
- Recent sales history is more important than older history

## What I Learned

This project taught me a lot about:
- How to approach time series forecasting problems
- The importance of feature engineering in ML
- How to handle large datasets efficiently
- Comparing different algorithms and picking the best one
- Thinking about real business problems (inventory optimization, supply chain)

## Business Value

This kind of forecasting helps retailers:
- Keep the right amount of stock (not too much, not too little)
- Plan warehouse space better
- Schedule deliveries more efficiently
- Reduce costs from waste and stockouts
- Keep customers happy by having products available

## How to Run

1. Clone this repo
2. Install requirements: `pip install -r requirements.txt`
3. Download the dataset from Kaggle
4. Run the Jupyter notebook step by step

---

I built this project to learn practical machine learning for business problems. I followed a tutorial initially but implemented everything myself and experimented with different approaches to really understand the concepts.
