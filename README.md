# 📊 Data-Driven Sales Trends

## Applying the APPASA Framework  
*(Ask – Prepare – Process – Analyze – Share – Act)*  

This project follows the framework I learned from **Google Data Analytics Professional Certficate**, where I ultilized the **APPASA** framework to transforming raw sales data into actionable business insights. My analysis leverages Python along with various libraries package like pandas, and visualization libraries to uncover key sales trends across a full year of data and provide recoommendations to the stakeholders.

---

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
5. **Filter logic:** Removed invalid rows such as “Order Date” text headers within the data.

**Tools Used**  
Python, pandas, numpy, matplotlib, seaborn, datetime.

---

## ANALYZE

### 1. Which month had the best sales, and how much revenue did it generate?
The dataset was grouped by month using `groupby('Month')` and total sales were summed.

- **Result:** December had the highest sales.  
- **Revenue:** Approximately **$4.6 million** (example value; replace with your real result).  
- **Insight:** This spike likely results from increased holiday shopping demand, making Q4 the most profitable quarter.  
  *<img width="617" height="478" alt="image" src="https://github.com/user-attachments/assets/d78c2a69-a6e8-4c8b-ae40-078b681b439e" />*

---

### 2. Which city achieved the highest sales overall?
Using the `Purchase Address` column, the city name was extracted to analyze regional performance.

- **Result:** San Francisco generated the highest overall revenue.  
- **Insight:** The city’s high population density and purchasing power may have contributed to stronger sales.  
- **Recommendation:** Focus future marketing efforts on high-performing urban areas.  
*(Insert your city sales bar chart here.)*

---

### 3. What time of day should advertisements be displayed to maximize purchases?
The `Order Date` column was converted to datetime, and the hour was extracted to identify when customers placed orders.

- **Result:** Peak order times were between **10 a.m. and 7 p.m.**  
- **Insight:** Sales activity rises steadily through the morning, peaking in the early evening.  
- **Recommendation:** Schedule online ads and email promotions during these hours to increase conversion rates.  
*(Insert your hourly sales line plot here.)*

---

### 4. Which products are most often sold together?
By identifying orders with duplicate `Order ID`s, combinations of products bought together were analyzed using `itertools.combinations` and `Counter`.

- **Result:**  
  - **iPhone** and **Lightning Charging Cable** were most frequently purchased together.  
  - **Google Phone** and **USB-C Cable** also appeared often.  
- **Insight:** Customers tend to buy accessories alongside main products, suggesting strong cross-sell opportunities.  
- **Recommendation:** Offer bundle deals or “frequently bought together” promotions.  
*(Insert your product pair chart here.)*

---

### 5. Which product sold the most, and why?
Product quantities were summed and compared to price per unit to understand demand patterns.

- **Result:** **AAA Batteries (4-pack)** were the most sold item by volume.  
- **Insight:**  
  - Lower-priced essential items drive higher quantity sales.  
  - Products with lower unit prices sell in larger volumes but contribute less to total revenue compared to high-ticket items.  
- **Recommendation:** Maintain stock availability for frequently purchased, low-cost items while promoting accessories with high profit margins.  
*(Insert your product quantity bar chart here.)*

---

## SHARE
**Deliverables**  
- Jupyter Notebook containing all analysis steps, code, and visualizations.  
- Graphs and charts clearly showing results for each question.  
- Summary of key findings and recommendations.

**Intended Audience**  
Sales management, marketing team, and decision-makers who use data-driven insights to improve strategy.

---

## ACT
**Recommended Business Actions**  
1. Prepare for higher sales volume in December and during holiday seasons.  
2. Target major urban areas like San Francisco for marketing and logistics support.  
3. Schedule digital advertising during peak hours between 10 a.m. and 7 p.m.  
4. Create product bundles for popular accessory combinations.  
5. Keep essential, low-cost items well-stocked and promote high-margin products through cross-selling.
