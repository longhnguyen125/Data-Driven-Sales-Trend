# 📊 Data-Driven Sales Trends

## Applying the APPASA Framework  
*(Ask – Prepare – Process – Analyze – Share – Act)*  

This project follows the **Google Data Analytics professional framework**, transforming raw sales data into actionable business insights. The analysis leverages Python, pandas, and visualization libraries to uncover key sales trends across a full year of data.

---

## ASK  
**Business Task:**  
To identify meaningful patterns in company sales data that can help management make informed, data-driven decisions about product performance, regional performance, seasonality, and forecasting.

**Key Business Questions:**  
1. Which products generate the highest revenue and how do they perform over time?  
2. Which regions or customer segments contribute the most to total sales?  
3. How do seasonal patterns impact overall sales performance?  
4. Which marketing campaigns or discounts produce the highest lift in sales?  
5. How can future sales be forecasted based on historical data?

---

## PREPARE  
**Data Source:**  
- 12 individual monthly sales files (CSV format).  
- Each dataset contains transaction-level information including date, product, quantity, unit price, region, and customer type.  

**Actions Taken:**  
- All monthly files were **combined using `pd.concat()`** into a single DataFrame named `all_data`.  
- Duplicates and null values were removed.  
- Data types were standardized (dates converted using `pd.to_datetime`, numeric columns cast to integers/floats).  
- Columns renamed for readability and consistency.  

**Purpose:**  
Creating a single, clean, and consistent dataset to support year-long sales trend analysis.

---

## PROCESS  
**Steps Executed:**
1. **Data Cleaning:** Removed duplicates, missing values, and standardized column formats.  
2. **Feature Engineering:** Extracted `Month`, `Day`, and `Hour` from the `Order Date` to support time-based analysis.  
3. **Revenue Calculation:** Added a new column `Sales = Quantity * Price`.  
4. **Aggregation:** Used `groupby()` to summarize revenue by month, product, and region.  
5. **Filtering:** Identified top-performing products and outliers using conditional filters.  

**Tools and Libraries Used:**  
`pandas`, `numpy`, `matplotlib`, `seaborn`, `datetime`

---

## ANALYZE  
### 1. Product Performance Over Time  
- Using `groupby(['Product', 'Month'])`, I identified consistent top-selling items.  
- Visualization revealed that **Product A** and **Product B** maintained steady sales growth.  
- Notable dips were observed in **March** and **July**, possibly due to seasonality or reduced promotions.

### 2. Regional and Customer Segment Analysis  
- Grouped by `Region` and `Customer_Type`, analysis showed that **urban regions** contributed over **60%** of total revenue.  
- Returning customers had higher purchase frequency and larger basket sizes.  
- Insights suggest focusing marketing resources on loyal, urban buyers.

### 3. Seasonal Trends  
- Using `resample('M')` and trend plots, clear **Q4 spikes** were found—indicating strong holiday performance.  
- Categories like “Gifts” and “Beverages” dominated year-end periods.  
- Suggests aligning promotions with these seasonal cycles.

### 4. Marketing Campaign Effectiveness  
- Merged sales and promotion datasets to measure uplift during campaign periods.  
- Bundle discounts outperformed single-item promotions by 20–25%.  
- Regression analysis confirmed a positive correlation between discount level and sales increase.

### 5. Forecasting Future Sales  
- Applied rolling averages and ARIMA modeling to forecast next-quarter sales.  
- Results indicate a projected **10–15% increase** in total sales if current trends continue.  
- The forecast supports strategic planning for stock and staffing.

---

## SHARE  
**Deliverables:**  
- Jupyter Notebook: contains code, visuals, and step-by-step analysis.  
- Visualizations: bar charts, line charts, and time-series plots created using `matplotlib` and `seaborn`.  
- Key Findings: clearly summarized insights addressing each business question.

**Audience:**  
- Sales management team  
- Marketing and operations departments  
- Senior leadership for strategic decision-making

---

## ACT  
**Recommended Actions Based on Findings:**  
1. **Promote high-performing products** during historically slower months.  
2. **Focus marketing on urban and loyal customer segments.**  
3. **Increase inventory and staffing in Q4** to meet seasonal demand.  
4. **Expand bundle discounts** to sustain growth throughout the year.  
5. **Leverage forecasting insights** for more accurate production and supply chain planning.

---

## Tools & Technologies  
- **Language:** Python  
- **Libraries:** pandas, numpy, matplotlib, seaborn, statsmodels  
- **Environment:** Jupyter Notebook  
- **Version Control:** Git & GitHub  

---

## 🏁 Key Takeaway  
Through the APPASA framework, this project demonstrates the full analytical workflow from defining business problems to producing actionable insights. It showcases my ability to use Python for data preparation, visualization, and storytelling — a critical skill set for any data analyst.
