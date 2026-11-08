
# Global Superstore Operational Performance Analysis

Author: Apollinaria Konstantinell
License: MIT

An exploratory data analysis (EDA) and time-series investigation examining transaction volumes, macro financial structures, product category distributions, and operational friction variables across a sample of historical records from 2012 - 2016 using Python, Pandas, and visualization frameworks.

 # Project Overview

The project analyses 1,000 unique transaction entries across 24 attributes from a historical sample spanning 2012 to early 2016.

#### What this project covers
• Loading and cleaning of sales data
• Handling of missing data through removal high-sparsity column (80% NaN values)
• Datatype validation and removal of customer PII (Customer Name) as well as other unnecessary attibutes.
• Tracking transaction volume and gross financial performance across product categories, sub-categories, regions and top/bottom 5 products.
• Identifying pricing anomalies, margin-draining revenue traps, and localized capital losses.
• Time-Series analysis of transaction volumes for  2012 - 2015.
• Seasonal line-plot mappings and correlation models evaluating promotional markdowns and logistical overhead.
• Clear visual summaries (bar charts & line graphs) stored in Asset/ folder.
• Full PDF report is available in Docs/ folder.
• Detailed documentation of the full analysis approach and methodology.

# Analysis Approach
A complete step-by-step breakdown of the analytical methodology used in this project is available here:
> Docs/ANALYSIS_APPROACH.md

#### This document covers:
• Data loading and cleaning process.
• Missing values handling and data pruning
• Descriptive statistics and overview of transaction volume and financial performance 
• Time-series visualisation approach
• Statistical validation
• Seasonal decomposition and seasonality line graph
• Dual analysis of sales v profit/loss
• Key takeaways and interpretation of findings

# Dataset Information
File: Dataset/Raw/Global_Superstore.csv
| :Column: | :Description: |
| :Order ID: | :Transaction assigned unique number: |
| :Order Date: | :Date order was placed (2012-01-08 onwards): |
| :Ship Date: | :Date the order was shipped (2012-01-13 onwards): |
| :Customer ID: | :Customer assigned unique number: |
| :Region: | :Geographical region of operation: |
| :Product ID: | :Product assigned unique number: |
| :Category: | :Main category of company inventory: |
| :Sub-Category: | :Sub-category of company inventory: |
| :Product Name: | :Unique product names: |
| :Sales: | :Sales amount per order: |
| :Quantity: | :Quantity of product(s) sold: |
| :Discount: | :Markdown percentage: |
| :Profit: | :Gross profit amount made on the sale of the order: |
| :Shipping Cost: | :Cost of shipping the order: |

This dataset contains sales volume and profits across operational regions over the sample years of 2012 - 2015 (Order dates) allowing for temporal and efficiency metrics analysis.

# Key Findings from the Analysis

#### Macro Volume vs. Return
Total gross sales reached £1,710,971.47, yielding a combined return of £288,920.44, highlighting a gap between volume and net efficiency.

#### Category Performance
• Technology: £756,983.02 sales, 19.2% profit margin.
• Furniture: £601,492.31 sales, 13.7% profit margin.
• Office Supplies: £352,496.14 sales, 17.5% margin (with high-margin anomalies like Fasteners at 48.0% and Paper at 44.4%).

#### Statistical Friction Validation
Discount rates correlate negatively with net returns (-0.51), while shipping costs per unit correlate at -0.60 with profit margins.

#### Revenue Leaks
• The Tables sub-category yields a thin 7.3% margin despite high sales due to a 16.8% markdown rate and £63.13 shipping drag per unit.
• Product with the highest sales volume with Profit Margin at -126.7%, is "Barricks Conference Table, Rectangular" its Discount is 70.0% and Shipping Cost of £48.76.

#### Implications
Primary bottle-neck Statistical validation confirms to the extend of our sample, that both promotional pricing and logistical margins create a moderate impact on profitability, with high shipping costs represent largest structural constraint on the business. Significant regional and categorical sectors for company operations are: Oceania for Furniture, Western Europe for Office Supplies and Western Europe for Technology. Looking at time-series seasonality graphs, we can confirm sharp uptake in purchasing volumes during Q2, beginging of Q3 while dropping during the end of Q3 before peaking once again in Q4, across the given years of 2012 - 2015. This showcases the operational stress peaks.

# How to Run the Analysis

1. Instal Miniconda alternatively Anaconda [click here](https://www.anaconda.com/download) see bottom of the webpage
   
2. Download the raw .ipynb file: Notebooks/GlobalMart Sales Performance EDA.ipynb
   
3. Launch Anaconda > Launch Jupyter Notebook
   
4. In browser Home page open the .ipynb file

# Technologies Used
Python
Pandas – data loading and manipulation
NumPy – numerical operations
Matplotlib & Seaborn – data visualization
Statsmodels.tsa.seasonal – seasonal decomposition
Jupyter Notebook – interactive analysis and documentation application

# Visual Outputs
Graph screenshots and key visualizations from the notebook are stored in the Asset/ folder.
A complete written report (including both code explanations and visuals) is available as a PDF in the Docs/ folder.
A detailed explanation of the full analysis methodology can be found in [Docs/ANALYSIS_APPROACH.md](Docs/ANALYSIS_APPROACH.md)

# License
This project is released under the MIT License. See the [LICENSE](LICENSE) file for full details.

# Author
Apollinaria Konstantinell [click here](https://github.com/ApolloKonstantinell)
