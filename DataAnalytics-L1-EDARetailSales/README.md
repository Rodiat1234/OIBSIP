# Exploratory Data Analysis on Retail Sales Data

**Oasis Infobyte Data Analytics Internship | Level 1, Task 1**

**Intern:** Rodiat Jimoh

## Objective
Explore an e-commerce sales dataset to understand sales trends, who the customers are, which product categories earn the most, and which variables are related, then turn the findings into business recommendations.

## Dataset
E-commerce customer behaviour data: 5,000 transactions from 1 January 2023 to 26 March 2024. All amounts are in Turkish Lira (TRY).

Source: Kaggle, "E-Commerce Customer Behavior and Sales Analysis" by umuttuygurr: https://www.kaggle.com/datasets/umuttuygurr/e-commerce-customer-behavior-and-sales-analysis-tr

## Tools Used
Python, pandas, matplotlib, seaborn, Jupyter Notebook

## Steps I Followed
1. **Loaded and inspected** the data (shape, data types, missing values).
2. **Descriptive statistics:** mean, median, mode, and standard deviation of the numerical columns.
3. **Sales trends:** converted `Date` to a datetime type, then plotted monthly and quarterly sales.
4. **Customer demographics:** age distribution and gender breakdown.
5. **Product analysis:** revenue and share of revenue by product category.
6. **Correlation heatmap** of the numerical variables.
7. **Additional visualisation:** average spend per transaction by category.
8. **Conclusions and recommendations.**

## Visualisations

### Monthly Sales Trend
![Monthly sales trend](EDA%201.png)

### Quarterly Sales Trend
![Quarterly sales trend](EDA%202.png)

### Distribution of Customer Age
![Age distribution](EDA%203.png)

### Customers by Gender
![Customers by gender](EDA%204.png)

### Revenue by Product Category
![Revenue by product category](EDA%205.png)

### Correlation Heatmap
![Correlation heatmap](EDA%206.png)

### Average Spend per Transaction by Category
![Average spend by category](EDA%207.png)

## Key Findings
- **Sales trend:** monthly sales ranged from about 257,000 TRY (April 2023) to about 397,000 TRY (January 2024). The weakest quarter was 2023 Q2, and the strongest was 2023 Q4.
- **Customers:** about 82% of transactions come from customers aged 18 to 45, and the 26-35 group is the largest (30.28%). Gender is almost evenly split: female 49.84%, male 48.70%, other 1.46%.
- **Products:** Electronics brings in 47.38% of revenue, and the top three categories (Electronics, Home & Garden, Sports) bring in 81.21%.
- **Why Electronics leads:** every category has a similar number of transactions (about 610 to 667), but the average Electronics purchase is about 3,732 TRY, compared with about 118 TRY for Books.
- **Relationships:** total amount is strongly linked to unit price (0.79). Age, delivery time, session length, and pages viewed show almost no relationship with spending or customer rating.
- **Skewed spending:** the average transaction is about 983 TRY, but the median is only about 338 TRY, because a few very large purchases pull the average up.

## Recommendations
1. **Prioritise Electronics** in stock and marketing, while tracking its sales closely because revenue depends so heavily on one category.
2. **Focus marketing on customers aged 18-45**, especially 26-35, who make about 82% of purchases.
3. **Run promotions in the weak months** (April and September 2023) and prepare stock for the peaks (August, December, and January).
4. **Raise the value of low-spend categories** such as Sports, Books, and Food through bundling and upselling.
5. **Do not target marketing by gender**, since the split is almost even.

## Limitations
- The dataset has product categories but no individual product names, so the "top 10 best-selling products" analysis was replaced with a ranking of product categories by revenue.
- The data covers about 15 months, and March 2024 (and therefore Q1 2024) is incomplete.
- The "Other" gender group (73 transactions) and the oldest age group are small, so results for them should be read with care.
- Correlation does not prove cause and effect.

## How to Run
1. Install the libraries: `pip install pandas matplotlib seaborn`
2. Download the dataset (link above) and save it in the same folder as the notebook as `ecommerce_customer_behavior_dataset.csv`.
3. Open `DataAnalytics-L1-EDARetailSales.ipynb` in Jupyter Notebook and run all cells.
