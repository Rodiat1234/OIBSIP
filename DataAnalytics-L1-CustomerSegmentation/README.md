# Customer Segmentation Analysis (RFM + K-Means)

**Oasis Infobyte Data Analytics Internship | Level 1, Task 2**
**Intern:** Rodiat Jimoh

## Objective
Group an online retailer's customers into distinct segments based on their purchasing behaviour, so that each group can be given a suitable marketing action.

## Dataset
The "Online Retail" dataset, donated to the UCI Machine Learning Repository. It contains transactions from 1 December 2010 to 9 December 2011 for a UK-based online retailer. Prices are in sterling (£).

- **Original source:** Chen, D. (2015). Online Retail [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
- **Copy used:** `data.csv` from the Kaggle dataset "E-Commerce Data": https://www.kaggle.com/datasets/carrie1/ecommerce-data
- **License:** CC BY 4.0

Columns used: `InvoiceNo`, `InvoiceDate`, `Quantity`, `UnitPrice`, `CustomerID`.

## Tools Used
Python, pandas, numpy, scikit-learn (StandardScaler, KMeans), matplotlib, seaborn, Jupyter Notebook

## Steps I Followed
1. **Loaded and inspected** the data (541,909 rows, 8 columns).
2. **Cleaned the data:**
   - Removed returns and rows with a zero or negative quantity or price (541,909 to 530,104 rows).
   - Removed rows with no customer ID (530,104 to 397,884 rows).
   - Converted `InvoiceDate` to a datetime type.
3. **Descriptive statistics:** average purchase value, purchase frequency, and customer lifetime value.
4. **Built RFM features** for each of the 4,338 customers:
   - **Recency:** days since the customer's last purchase.
   - **Frequency:** number of unique orders.
   - **Monetary:** total spend.
5. **Scaled the features:** applied a log transform to reduce skew, then StandardScaler.
6. **Chose the number of clusters** with the Elbow Method (K = 3).
7. **Ran K-Means** and added each customer's cluster to the table.
8. **Visualised and profiled the clusters** with scatter plots, a profile table, and a bar chart.

## Visualisations

### Elbow Method
![Elbow plot](CS%2011B.png)

### Clusters: Recency vs Monetary
![Recency vs Monetary](CS%2012B.png)

### Clusters: Frequency vs Monetary
![Frequency vs Monetary](CS%2012C.png)

### Customers per Cluster
![Customers per cluster](CS%20bar%20chart.png)

## Results

| Segment | Customers | Avg Recency (days) | Avg Frequency (orders) | Avg Monetary |
|---|---|---|---|---|
| High-Value | 776 (17.9%) | 17.07 | 13.27 | 7,865.64 |
| Regular | 1,696 (39.1%) | 44.46 | 3.37 | 1,257.69 |
| At-Risk | 1,866 (43.0%) | 167.61 | 1.35 | 361.54 |

## Key Findings
- The **High-Value** group is the smallest, but brings in roughly two thirds of total spend.
- The **At-Risk** group is the largest, but spends the least and last bought about 168 days ago on average.
- The **Regular** group has the most room to grow.

## Marketing Recommendations
- **High-Value:** loyalty or VIP programme, early access to new products, priority service.
- **Regular:** product bundles, minimum-spend offers, and reminder emails to encourage repeat purchases.
- **At-Risk:** win-back emails with a limited-time offer, and a short survey to find out why they stopped buying.

## Limitations
- The Elbow curve has no single sharp bend, so K = 3 was chosen for interpretability.
- Clusters overlap at their edges, especially Regular and At-Risk.
- The analysis uses only Recency, Frequency, and Monetary, so it cannot say what customers buy or why.
- Rows with no customer ID (about 25%) and returns were removed.

## How to Run
1. Install the libraries: `pip install pandas numpy matplotlib seaborn scikit-learn`
2. Download the dataset (link above) and save it as `data.csv` in the same folder as the notebook.
3. Open `Customer_Segmentation.ipynb` in Jupyter Notebook and run all cells.

