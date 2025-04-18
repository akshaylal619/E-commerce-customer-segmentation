# E-commerce-customer-segmentation
A comprehensive analysis of customer segmentation of various e-commerce sites to categorize customers based on their purchasing behavior using the RFM model (Recency, Frequency, and Monetary value) in order to enable personalized marketing strategies and improve customer retention.



## Objective

To identify and categorize customers using the RFM model for better targeting, improved retention, and personalized engagement strategies.

---

## Dataset Overview

The dataset simulates e-commerce transactions with the following key fields:

- `CustomerID`: Unique identifier for each customer  
- `InvoiceNo`: Transaction number  
- `InvoiceDate`: Date of purchase  
- `Quantity`: Number of items purchased  
- `UnitPrice`: Price per item  
- `TotalPrice`: Calculated as `Quantity × UnitPrice`

---

## Data Cleaning Steps

- Removed rows with missing `CustomerID`
- Filtered out records with `Quantity <= 0`
- Created a new column `TotalPrice`

---

## RFM Metrics & SQL

The RFM metrics were calculated using SQL:

- **Recency**: Days since last purchase (as of `2025-02-01`)
- **Frequency**: Number of unique transactions
- **Monetary**: Total amount spent by each customer


---

## RFM Scoring

Each RFM metric is divided into 5 quantiles (scores from 1 to 5):

- **Recency**: Lower value = higher score
- **Frequency & Monetary**: Higher value = higher score

The scores are combined into an RFM Score (e.g., `555`, `431`, etc.)

---

## Customer Segments

| Segment             | RFM Score Pattern | Description                              |
|---------------------|-------------------|------------------------------------------|
| Champions           | 555, 554, 545     | Recent, frequent, high spenders          |
| Loyal Customers     | 444–555           | Consistent and high-value buyers         |
| New Customers       | R=5, F ≤ 2        | Recent but not frequent                  |
| At Risk             | R ≤ 2             | Previously active, now inactive          |
| Lost                | 111               | Long inactive with low value             |
| Potential Loyalists | F ≥ 3, M ≥ 3      | Good potential to become loyal customers |

---

## Key Insights

- **Champions (31.3%)** contributed nearly 40% of total revenue  
- **Loyal Customers (24%)** show stable purchasing behavior  
- **Potential loyalist (22.6%)** can be re-engaged through special offers  
- **Needs attention (22.1)** may benefit from win-back campaigns

---

