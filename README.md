# Customer Purchase Segmentation using K-Means Clustering

Segments mall customers into distinct groups based on **annual income** and **spending score**, using the K-Means clustering algorithm. The notebook walks through data exploration, finding the optimal number of clusters, fitting the model, and profiling each customer segment for marketing insights.

## Dataset

[Mall Customer Segmentation Data](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) (`Mall_Customers.csv`), containing `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, and `Spending Score (1-100)` for 200 mall customers.

Download the CSV from Kaggle and place it in the project root (or update `DATA_PATH` in the notebook to point to its location).

## Project structure

```
.
├── Customer_Purchase_Segmentation_KMeans.ipynb   # main analysis notebook
├── requirements.txt                              # Python dependencies
├── Mall_Customers.csv                            # dataset (not included, see above)
└── README.md
```

## Setup

```bash
git clone <your-repo-url>
cd <your-repo-name>
python -m venv venv
source venv/bin/activate        # on Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook Customer_Purchase_Segmentation_KMeans.ipynb
```

## Approach

1. **Load and explore** the data, check for missing values and basic statistics.
2. **Clean and prepare** the data — rename columns, set aside `Gender` for later profiling.
3. **Visualize** relationships between age, income, and spending score.
4. **Find the optimal number of clusters** using the elbow method (WCSS / inertia) and silhouette score as a cross-check.
5. **Fit the final K-Means model** with the chosen `k`.
6. **Visualize the clusters** with centroids overlaid.
7. **Profile each segment** (mean age, income, score, and size) to interpret what each cluster represents.

## Example segments

K-Means typically identifies five intuitive groups:

- High income, high spending — premium customers, prime targets for loyalty programs
- High income, low spending — potential customers needing targeted marketing
- Low income, high spending — price-sensitive but engaged shoppers
- Low income, low spending — lowest priority segment
- Average income, average spending — the general customer base

## Possible extensions

- Include `age` and `gender` in the clustering, with feature scaling (`StandardScaler`)
- Compare against other algorithms (DBSCAN, hierarchical clustering)
- Validate segments against real business outcomes (e.g. campaign response rates)

## Requirements

See [`requirements.txt`](requirements.txt) — pandas, numpy, matplotlib, seaborn, scikit-learn, kneed.

## License

MIT (or update to your preferred license).
