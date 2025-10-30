# 📊 Data-Driven Sales Trends

## Applying the APPASA Framework  
*(Ask – Prepare – Process – Analyze – Share – Act)*  

This project follows the framework I learned from **Google Data Analytics Professional Certficate**, where I ultilized the **APPASA** framework to transforming raw sales data into actionable business insights. My analysis leverages Python along with various libraries package like pandas, and visualization libraries to uncover key sales trends across a full year of data and provide recommendations to the stakeholders.

---
## ASK

After a thorough conversation with stakeholders. Here is the five questions that the company would like to know:
1. Which month has the best sales? How much does it earn?
2. What city has the best sales?
3. What time should we display advertisement to maximize the likelihood of customer's buying our product?
4. What products are most often sold together?
5. What kind of product sold the most? Why is it?




## PREPARE
**Data Source**  
Twelve monthly sales CSV files covering a full year of transactions.  
Each file includes **order date**, **product name**, **quantity**, **price**, and **purchase address**.

**Data Preparation Steps**  
- Combined all 12 monthly files into a single dataset using `pd.concat()` for comprehensive yearly analysis.  
- Cleaned the dataset by removing duplicates and handling missing values.  
- Converted columns to appropriate data types (`Order Date` to datetime, numeric columns to int/float).  
- Extracted useful information such as month, city, and hour from existing columns.  
- Created new calculated fields, including `Sales = Quantity * Price`.

This created a clean and consistent dataset ready for analysis.

---

## PROCESS
**Data Cleaning and Transformation**  
1. **Merge datasets:** Used `pd.concat()` to combine monthly data.  
2. **Handle missing data:** Removed rows with null values or incorrect entries.  
3. **Create calculated fields:** Added total sales column (`Sales = Quantity * Price`).  
4. **Extract features:**  
   - `Month` from `Order Date` for monthly trend analysis.  
   - `City` extracted from `Purchase Address` for geographic comparison.  
   - `Hour` extracted from `Order Date` for time-based insights.  

=> After concat all twelve months worth of sales data. This is a first look of the dataframe (df):
<img width="378" height="323" alt="Screenshot 2025-10-29 at 8 07 06 PM" src="https://github.com/user-attachments/assets/7494e5dc-561f-4972-b6b5-9f7ec45d6609" />


<img width="768" height="203" alt="Screenshot 2025-10-29 at 8 07 46 PM" src="https://github.com/user-attachments/assets/5e8c8908-9b22-4424-a655-05a7b66df255" />

---

## ANALYZE

### 1. Which month had the best sales, and how much revenue did it generate?
The dataset was grouped by month using `groupby('Month')` and total sales were summed.

- **Result:** December had the highest sales.  
- **Revenue:** Approximately **$4.6 million**.  
- **Insight:** This spike likely results from increased holiday shopping demand, making Q4 the most profitable quarter.
  
  *<img width="617" height="478" alt="image" src="https://github.com/user-attachments/assets/d78c2a69-a6e8-4c8b-ae40-078b681b439e" />*

---

### 2. Which city achieved the highest sales overall?
Using the `Purchase Address` column, the city name was extracted to analyze regional performance.

- **Result:** San Francisco generated the highest overall revenue. Follow-up by Los Angeles, then New York City. 
- **Insight:** The city’s high population density and purchasing power may have contributed to stronger sales.  
- **Recommendation:** Focus future marketing efforts on high-performing urban areas.
  
*<img width="632" height="500" alt="image" src="https://github.com/user-attachments/assets/9b2461c1-9e2c-4be3-a144-21f3d0bdf997" />*

---

### 3. What time of day should advertisements be displayed to maximize purchases?
The `Order Date` column was converted to datetime, and the hour was extracted to identify when customers placed orders.

- **Result:** Peak order times were between **10 a.m. and 7 p.m.**  
- **Insight:** Sales activity rises steadily through the morning, peaking during lunch and dinner time.  
- **Recommendation:** The company should display our ads during lunch hours from 11:00 PM to 12:00 PM, as well as 6:00 PM to 7:00 PM. Because those two range of hours are peak time, therefore the customer likely to place order.
        
*<img width="632" height="470" alt="image" src="https://github.com/user-attachments/assets/c9b352c1-ffff-4e4f-aea8-74508931ff69" />*

---

### 4. Which products are most often sold together?
To find which products customers tend to buy together, I looked for orders that had the same `Order ID`.  
Each `Order ID` represents a single transaction, so if multiple items share the same `Order ID`, they were bought together.

- **Result:**  
  - **iPhone** and **Lightning Charging Cable** were most frequently purchased together.  
  - **Google Phone** and **USB-C Cable** also appeared often.  
- **Insight:** Customers tend to buy accessories alongside main products, suggesting strong cross-sell opportunities.  
- **Recommendation:** In order to maximize our revenue, and reduce the number of items left over in inventory, I believe the management should combine and sell most selling product with least selling product at a discount price.
  
  *<img width="454" height="217" alt="image" src="https://github.com/user-attachments/assets/0120bb34-9668-4934-8167-7ee14bc9dfed" />*

---

### 5. Which product sold the most, and why?
Product quantities were summed and compared to price per unit to understand demand patterns.

- **Result:** USB-C Charging Cable /  Lightnight Charging Cable / AAA Batteries (4-packs) are the most sold item by volume with over 20,000+ quantities.  
- **Insight:**  
  - Lower-priced essential items drive higher quantity sales.  
  - Products with lower unit prices sell in larger volumes but contribute less to total revenue compared to high-ticket items.
  - Or this could be the quality of the product. 
- **Recommendation:** Maintain stock availability for frequently purchased, low-cost items while promoting accessories with high profit margins.
  
  *<img width="592" height="609" alt="image" src="https://github.com/user-attachments/assets/057821ca-b509-4133-9b36-c456ce9f3849" />*

---

## SHARE

**Audience**  
Sales management, marketing team, and executives.

---

## ACT
**Recommended Business Actions**  
1. Prepare for higher sales volume in December and during holiday seasons.  
2. Target major urban areas like San Francisco for marketing and logistics support. 
3. Schedule digital advertising during peak hours during lunch time (11 AM to 12 PM) and dinner time (7 PM to 8 PM).  
4. Create product bundles for popular accessory combine with least selling product. By doing so, the company can save inventory cost while increasing revenue.
5. Maintain stock availability for frequently purchased, low-cost items while promoting accessories with high profit margins.
