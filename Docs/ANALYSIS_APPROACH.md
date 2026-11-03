Author: Apollinaria Konstantinell
Project: Global Superstore Portfolio Exploratory Data Analysis (EDA)
Dataset: xxx

# 1. Objective
The primary goal of this analysis was to evaluate operational sales volume against profitability for a global retailer. 
By diagnosing financial drag factors, temporal patterns, and geographic distribution from a sample dataset.

# 2. Dataset Overview
  • Source File: xxx (Sample Size)
  • Records: 1,000 observations
  • Time Period: 2012 – 2015 (with shipping trailing into January 2016)
  • Key Variables: 
    * Sales
    * Quantity
    * Discount
    * Profit
    * Shipping Cost

# 3. Analysis Workflow

#### Step 1. Environment Setup & Imports
Required libraries were imported for data manipulation, visualization, and statistical analysis:
  • pandas & numpy - data handling
  • matplotlib.pyplot & seaborn - visualisation
  • statsmodels.tsa.seasonal - time-series econometrics and decomposition

#### Step 2. Data Loading
The dataset was loaded using pd.read_csv().

#### Step 3. Initial Sample Data Exploration
  * Examined the first 15 rows with .head()
  * Identified the shape and structure of the data
  * Checked data types and basic statistics with .info() and .describe().T
  • Checked the last 15 rows with .tails() for NaN values and other data inconsistensies 

#### Step 4. Handling Missing Values
* Checked for missing values. Postal Code column is ideantified as the only one that hold NaN values (with 80% values missing). We dorp the column as is it unusable and is not necessary to our analysis.

#### Step 5. Security & Anonymization 
Dropped the Customer Name variable to maintain strict data privacy standards, as well as redundant columns:
    * Row ID
    * City
    * State
    * Country
    * Market
    * Ship Mode
    * Segment
    * Order Priority

#### Step 6. Uniqueness Validation
Ran df.duplicated() to verify that rows were uniquely indexed, confirming 0% duplicate presence.

#### Step 7. Data Type Conversion
  * Converted Order Date, Ship Date columns from flat objects into datetime64[ns] using pd.to_datetime.
  * Established a timeline by Order Date to map out sample lifetime.

#### Step 8. Descriptive Parametric Statistics
Consolidated absolute sum-totals for Sales and Profit across categorical fields of Category, Sub-Category, Region. Also generated upper and lower tail arrays (.head(5) and .tail(5)) to isolate top and bottom performing products.

Key Observartion(s):
  * Total Sales to Total Profits the difference is £142,2051.03
  * Looking into the Sub-Categories, we can see Supplies: Sales: £2,037.92, Profit: -£89.85
  
#### Step 9. Portfolio Efficiency Matrix
To balance the volume metrics against profit amounts, created a matrix with profit margin percentage and shipping cost per unit to explore the data by Sub-Category.
Filtered product rankings by global median sales value cuts to exclude extreme outliers on low level of detail variables, while mean was used on high level of detail variables.
In individual breakdowns (Operational Friction Analysis by Sub-Category and Operational Friction Analysis: Negative Profit Products by Profit Margin %) only mean was used for measure of central tendency.

Key Observation(s):
  * Top performing sub-categories: Phones, Appliances, Bookcases have quiet the high shipping cost, but it can be explained with the vlaue and the size of the items shipped.
  * Sub-categories with sevearly low or even negative Profit Margins: Tables, 7.3% Prifit Margin, 16.8% Discount and sitting at £63.13 and Supplies (that also have quiet low sales overall, sitting at £2,037.92 only), with Profit Margin at -4.4%, Discount at 8.6% and Shipping Cost at £14.37
  * Six products, all with Profit Margin above -100% and one (Intertable Tab Indexes For Data Binders) sitting at -169.6% Profit Margin, are being marked down by 60% - 80%
  * Product with the highest sales volume with Profit Margin at -126.7%, is Barricks Conference Table, Rectangular, its Discount is 70.0% and Shipping Cost of £48.76
  * Product with highest sales volume is Hoover Stove, White, Sales: £21,179.89, Profit Margin of -11.1%, Discount 17.4% and Shipping Cost of £62.78 

Consiceding wearehousing costs and logistics, this item alone is (if still being sold) is taking up space and money that could be reallocated to profitable items

#### Step 10. Statistical Validation (Bivariate Correlation)
Calculated linear covariance relationships to statistically show the strength and direction of margin degradation
Results:
  * Overall Discount Correlation (Discount v Profit): -0.51
  * Sub-Category Shipping Cost Correlation (Shipping Cost per Unit v Profit Margin %): -0.60
  * Conclusion: There is a moderately strong negative correlation, meaning that when f ex discount goes up, profit goes down.

#### Step 11. A Look Into Negative Profit Products by Profit Margin
Looking a closer look at the products with negative profit margin that are available to us inthis sample dataset, to get some understanding of revenue traps.

Key Observation(s):
  * There six products, all with Profit Margin above -100% and one (Intertable Tab Indexes For Data Binders) sitting at -169.6% Profit Margin, are being marked down by 60% - 80%
  * Product with the highest sales volume with Profit Margin at -126.7%, is Barricks Conference Table, Rectangular, its Discount is 70.0% and Shipping Cost of £48.76 
  * Product with highest overal sales volume is Hoover Stove, White, Sales: £21,179.89, Profit Margin of -11.1%, Discount 17.4% and Shipping Cost of £62.78

    
#### Step 12. Visualisation of Total Sales by Category
Created a bar chart to visually compare the total gross sales for each category, providing a stakeholder friendly view.

#### Step 13. Regional Sales Performance Heatmap
Visualised a heatmap of total sales by regions (vertical axis) and categories (horizontal axis). Providing an easy to read breakdown of global sales for the company.

#### Step 14. Time-Series Analysis of Monthly (gross) Sales Over Time
Created a simple line graph to clearly show the overal trend for monthly sales over the years of operation as available to us in this sample data.

#### Step 15. Visualisation of Monthly Sales by Year
Visualised an overarching view of monthly sales trends, seasonality or unusual spikes, broken down by year.

#### Step 16. Visualisation of Seasonal Decomposition
Used seasonal_decompose to produce seasonal decomposition model to analyse Trends, Seasonality and Residual data points.

#### Step 17. Visualisation of Dual Analysis Transaction Volume (Sales) vs Return (Profit)
Created a visualisation of a comprehensive picture of the Operational Friction Analysis to gain more acceccisble understading of the ammount of profitable vs depleading sales transactions.

# 4. Applied Tools & Techniques

| :Technique: | :Purpose: |
| :Descriptive Statistics: | :Base line understanding of the data set: |
| :GroupBy Aggregation: | :Compare various business buckets: |
| :Correlation Analysis: | :Explore relationship between discount/shipping cost and final return: |
| :Bar Chart & Line Graphs: | :Visual representation of findings: |
| :Data Purge: | :Removal of columns unnecessary to the analysis: |
| :Datetime Convertion: | :Enable temporal analysis: |

# 5. Critical Technical Takeaways

1. Data Quality First - pre-processing to prevent errors in later stages of analysis.
2. Robust Averages - using a mixture of median profit margins for low level of detail categories and mean for products to protect the global figures from being skewed by high-volume sales anomalies while enabling full level of scewness in granullar levels.
3. Statistics & Visualisation - combined visual storytelling with rigorous statistical testing.
4. Actionable Insights – Focused on findings that support real-world environmental decision-making.

# 6. Files Related to this Analysis

* Full interactive anaysis: [GlobalMart Sales Performance EDA.ipynb](https://github.com/user-attachments/files/34338123/GlobalMart.Sales.Performance.EDA.ipynb)
* PDF Report: Docs/GlobalMart Sales Performance EDA.pdf
* Visualisation screenshot: Assets/
* Dataset: Dataset/Raw/Global_Superstore.csv

This document outlines the structured analytical approach followed throughout the project.
