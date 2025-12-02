# E-Commerce Customer Analytics: Segmentation, Market Basket Mining, and Sales Forecasting
This project implements a comprehensive e-commerce analytics pipeline focused on understanding customer behavior, identifying buying patterns, and predicting future sales trends using data mining and machine learning techniques.

## Dataset
**Source:** [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

The dataset contains transaction records from an online retail store with the following features:
- **Invoice**: 6-digit invoice number (prefix 'c' indicates cancellation)
- **StockCode**: 5-digit product code
- **Description**: Product name
- **Quantity**: Number of items purchased
- **InvoiceDate**: Transaction date and time
- **UnitPrice**: Product price per unit (in sterling)
- **CustomerID**: 5-digit unique customer identifier
- **Country**: Customer location

## Project Objectives
### 1. **Data Preparation & Cleaning** ✅
- Load and explore the Online Retail dataset
- Handle missing values and inconsistencies
- Remove non-product transactions (cancellations, adjustments, fees)
- Validate data quality and format

**Status**: Complete
- Dropped ~26.5% of raw data during cleaning
- Identified and removed administrative codes (POST, DOT, BANK CHARGES, etc.)
- Removed transactions with invalid Invoice numbers, missing CustomerIDs, and zero/negative prices

### 2. **RFM Analysis & Customer Segmentation** ✅
- Convert transaction-level data to customer-level summaries
- Calculate RFM (Recency, Frequency, Monetary) metrics
- Identify and handle outliers
- Apply K-Means clustering for customer segmentation

**Status**: Complete

#### Key Findings: Four Customer Segments
**Cluster 0 - "At-Risk" Customers** (Dark Red)
- Recency: 260 days (almost 9 months since last purchase)
- Frequency: Low (avg. 1-2 purchases)
- Monetary Value: Lowest
- Action: Churn prevention campaigns needed

**Cluster 1 - "Loyal Customers"** (Green)
- Recency: 48 days
- Frequency: Good (avg. 4 purchases)
- Monetary Value: Strong (avg. £1,153)
- Action: Retention and upselling opportunities

**Cluster 2 - "New/Potential Customers"** (Blue)
- Recency: 56 days
- Frequency: Very Low (avg. 1.6 purchases)
- Monetary Value: Low (avg. £390)
- Action: Engagement and conversion focus

**Cluster 3 - "Champions"** (Orange)
- Recency: 32 days (most recent)
- Frequency: Highest (avg. 7 purchases)
- Monetary Value: Highest (avg. £2,261)
- Action: VIP treatment and premium offerings

### 3. **Market Basket Analysis** ✅
- Identify product associations and buying patterns
- Calculate support, confidence, and lift metrics
- Generate association rules for cross-selling opportunities
- **Status**: Complete

### 4. **Sales Forecasting** ✅
- Time-series analysis of sales data
- Implement forecasting models (ARIMA, Prophet, LSTM)
- Predict future sales trends by product and customer segment
- **Status**: Complete

## Key Findings
### Data Quality Issues Addressed
Non-product transactions removed:
- Postage charges (POST, DOT)
- Discount codes (D)
- Carriage/shipping (C2)
- Manual entries (M, m)
- Bad debt (B) and samples (S)
- Bank and Amazon fees

**Cleaning Impact:**
- Starting records: ~541,909
- Final records: ~398,139 (~73.5% retained)
- Ensures dataset integrity for analysis

### Customer Insights
- 4 distinct customer behavioral segments identified using K-Means clustering
- Silhouette score optimization determined k=4 as optimal cluster count
- Clear differentiation in purchase behavior, spending patterns, and engagement levels

## Technical Stack
- **Language**: Python 3
- **Data Processing**: Pandas, NumPy
- **Machine Learning**: Scikit-learn
  - StandardScaler for feature normalization
  - KMeans for customer segmentation
  - Silhouette score for cluster validation
- **Association Rule Mining**: mlxtend
- **Forecasting**: statsmodels, prophet
- **Visualization**: Matplotlib, Seaborn, Plotly
- **Environment**: Jupyter Notebook

## Project Structure
```
E-commerce Customer Analytics/
├── README.md
├── requirements.txt
├── data/
│   ├── Online Retail.csv
│   └── online_retail_II.csv
├── notebooks/
    └── e_commerce_analytics.ipynb
```

## Requirements
See `requirements.txt` for all dependencies including:
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- jupyter

## Usage
### Running the Analysis
1. **Data Exploration & Cleaning** (Cells 1-40)
   - Execute cells in "Data Preparation & Cleaning" section
   - Validates data quality and removes invalid records

2. **RFM Analysis & Segmentation** (Cells 41-73)
   - Execute cells in "RFM Analysis & Customer Segmentation" section
   - Generates 4 distinct customer clusters
   - Produces visualizations for cluster characteristics

3. **Market Basket Analysis** (Cells 74+)
   - Execute cells in "Market Basket Analysis" section
   - Generates association rules
   - Identifies cross-selling opportunities

4. **Sales Forecasting** (Cells 90+)
   - Execute cells in "Sales Forecasting" section
   - Compare ARIMA, Prophet, and LSTM models
   - Visualize future sales trends
   - View geographical sales distribution map

## Results Summary
### Data Cleaning
- ✅ Removed cancellations and accounting entries
- ✅ Eliminated non-product transactions
- ✅ Handled missing values and outliers
- ✅ Validated transaction integrity

### Customer Segmentation
- ✅ Identified 4 optimal customer clusters
- ✅ Characterized each segment with actionable insights
- ✅ Created 3D visualizations of customer space
- ✅ Calculated descriptive statistics per segment

### Market Basket Analysis
- ✅ **Bundle Product Promotions**: Opportunities for discounted bundles (e.g., pink, green, and roses tea plates).
- ✅ **Optimize Product Placement**: Strategy to place strongly associated items adjacent to each other.
- ✅ **Inventory Management**: Importance of stocking complementary items together to avoid out-of-stock situations.

### Sales Forecasting
- ✅ **Model Performance**: Compared ARIMA, Prophet, and LSTM models for accuracy.
- ✅ **Trend Analysis**: Identified seasonal trends and long-term growth patterns in sales data.
- ✅ **Geographical Insights**: Mapped sales distribution to identify key markets and growth regions.

## Next Steps
1. **Advanced Deep Learning**
   - Implement Transformer-based models for forecasting
   - Explore multivariate time series analysis

## Future Work
1. **Visualization Dashboard**
   - Interactive dashboards using Plotly/Dash
   - Real-time customer segment tracking
   - Sales trend monitoring

2. **Recommendations Engine**
   - Product recommendations based on segment
   - Personalized marketing campaigns
   - Dynamic pricing strategies

## Author

**Neehanth Reddy Maramreddy**

## Course
Data Mining

## Notes

- Data is available on [UCI ML Repository](https://archive.ics.uci.edu/dataset/352/online+retail)
- Project implements comprehensive data mining workflow
- All analysis performed with Python in Jupyter Notebook environment
