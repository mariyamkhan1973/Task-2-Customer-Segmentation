# Task-2-Customer-Segmentation

# Customer Segmentation Using Unsupervised Learning — Mall Customers

Segmenting mall customers by spending habits using K-Means clustering, visualized with
PCA and t-SNE, with tailored marketing strategies proposed per segment.

##  Task Objective

Cluster customers based on age, income, and spending score, then propose relevant
marketing strategies for each identified segment.

##  Approach

1. **EDA** — examined the distribution of Age, Annual Income, and Spending Score, and
   confirmed low correlation between Income and Spending Score (motivating clustering
   over simple rules).
2. **Preprocessing** — standardized features (`StandardScaler`) before clustering.
3. **Choosing K** — used the Elbow Method and Silhouette Score across k=2..10 to justify
   the chosen number of clusters.
4. **Clustering** — applied `KMeans` with k=5.
5. **Visualization** — reduced dimensionality with PCA and t-SNE to visualize cluster
   separation in 2D.
6. **Strategy** — profiled each cluster's average age/income/spending and mapped each to
   a customer persona with a tailored marketing strategy.

## Results & Findings

Five clear, business-interpretable segments emerged:

| Segment | Marketing Strategy |
|---|---|
| Low income, low spending (Budget shoppers) | Discount alerts, value bundles, loyalty points |
| Low income, high spending (Impulsive young spenders) | Flash sales, social promos, BNPL |
| Medium income, medium spending (Average customers) | Seasonal campaigns, personalized cross-sell |
| High income, low spending (Careful affluent savers) | Premium/quality messaging, exclusive previews |
| High income, high spending (VIP customers) | Loyalty programs, early access, concierge service |

*(See the notebook's cluster profile table for exact cluster→persona mapping, as KMeans
cluster indices are arbitrary per run.)*

## Repository Structure

```
.
├── Customer_Segmentation.ipynb   # Full notebook: EDA → clustering → PCA/t-SNE → strategy
├── data/
│   └── Mall_Customers.csv        # Dataset (see note below)
├── requirements.txt
└── README.md
```

##  Note on the dataset

`data/Mall_Customers.csv` is a **synthetically generated dataset** built to match the
schema (`CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, `Spending Score (1-100)`) and
general cluster shape of the well-known Mall Customers dataset, since the real file
couldn't be downloaded in the environment this project was built in. To use the real
dataset, download it and replace `data/Mall_Customers.csv` — the notebook code runs
unchanged since column names match.

##  How to Run

```
pip install -r requirements.txt
jupyter notebook Customer_Segmentation.ipynb
```
