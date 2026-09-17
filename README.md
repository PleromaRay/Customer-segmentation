# Customer Segmentation

Unsupervised clustering of retail customers using spending behaviour, income, and purchase patterns.

The notebook groups **1,500 customers** into **4 segments**, compares KMeans with hierarchical clustering, and scores a new customer in real time.

**Notebook:** [Customer_segment.ipynb](Customer_segment.ipynb)

## What this project does

1. Loads and inspects `customer_segmentation_dataset.csv`
2. Cleans the data (drops `CustomerID` and `LoyaltyPoints`)
3. Explores numeric features
4. Scales numeric columns with `StandardScaler`
5. Encodes `Gender` and `PreferredCategory`
6. Chooses `k = 4` with the elbow method and silhouette scores
7. Fits **KMeans** and **Agglomerative Clustering**
8. Interprets each cluster and writes marketing recommendations
9. Saves `kmeans_model.pkl`, `scaler.pkl`, and `label_encoders.pkl`
10. Scores an example new customer

## Dataset

Expected file (same folder as the notebook):

`customer_segmentation_dataset.csv`

| Column | Description |
|---|---|
| Age | Customer age |
| AnnualIncome | Annual income |
| SpendingScore | Spending score |
| PurchaseFrequency | How often they buy |
| AverageBasketSize | Typical basket size |
| LoyaltyPoints | Loyalty balance (dropped before modelling) |
| PreferredCategory | Clothing, Luxury, Groceries, etc. |
| CustomerID | ID (dropped before modelling) |
| Gender | Male / Female |

1,500 rows, 9 columns, no missing values in the raw file used here.

## Segments

| Cluster | Profile | How to treat them |
|---|---|---|
| 0 | High income, high spend, frequent buyers — premium | Loyalty, exclusives, no heavy discounting |
| 1 | Low income, low spend, infrequent — price-sensitive | Entry prices, bundles, tight promotions |
| 2 | Occasional higher-spend / luxury-oriented buyers | Drops, gifting, convert to a second purchase |
| 3 | Mid income, moderate spend, regular shoppers | Subscriptions, reminders, consistent value |

Age does not separate the groups strongly.

## How to run

```bash
git clone https://github.com/PleromaRay/Customer-segmentation.git
cd Customer-segmentation
