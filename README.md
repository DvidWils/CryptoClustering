# Module19: Unsupervised Learning Challenge - Crypto Clustering Challenge

## Overview

This project applies unsupervised machine learning to cluster cryptocurrencies based on price volatility. K-Means clustering is applied to identify natural groupings among both a full feature set and a PCA-reduced feature set.

---

## Part 1: Find the Best Value for k by Using the Scaled DataFrame

- Used the **elbow method** with `k = 1 to 11`
- Plotted inertia values using `hvPlot` to visualize optimal `k`

**Question: What is the best value for `k`?**  
**Answer:** The best value for `k` is **4**, where the elbow appears in the curve.

---

## Part 2: Cluster the Cryptocurrencies with K-Means by Using the Scaled DataFrame

- Initialized KMeans model with `n_clusters=4`
- Fit the model on the scaled data
- Predicted clusters and added them to the DataFrame
- Created a scatter plot using:
  - `x = price_change_percentage_24h`
  - `y = price_change_percentage_7d`
  - `by = cluster` with `hover_cols = coin_id`

---

## Part 3: Optimize the Clusters with Principal Component Analysis

- Created PCA model with `n_components=3`
- Transformed the scaled data into 3 principal components
- Explained variance ratio:
  - **PC1 + PC2 + PC3 = variance ratio**
  -0.3719856 +  0.34700813 + 0.17603793 = 0.89500466 OR 89.50%

**Question: What is the total explained variance of the three principal components?**  
**Answer:** The total explained variance is approximately **89.50%**

- Created new PCA DataFrame with `coin_id` as index

---

## Part 4: Find the Best Value for k by Using the PCA DataFrame

- Repeated the elbow method on PCA-transformed data

**Question: What is the best value for k using PCA?**  
**Answer:** The best value for k is **4** — same as the original data.

**Question: Does it differ from the original k?**  
**Answer:** No, the best value for `k` is **4** in both cases.

---

## Part 5: Cluster the Cryptocurrencies with K-means by Using the PCA DataFrame

- Initialized KMeans model with `n_clusters=4`
- Fit the model using the PCA-reduced data
- Predicted and added cluster labels
- Created scatter plot using:
  - `x = PC1`
  - `y = PC2`
  - `by = cluster` with `hover_cols = coin_id`

---

## Part 6: Visualize and Compare Results

- Created composite elbow plot: original vs PCA
- Created composite cluster plot: original vs PCA

**Question: What is the impact of using fewer features to cluster the data using K-Means?**  
**Answer:**  
Using fewer features with PCA made the clusters easier to visualize. While the original clusters were more spread out and sometimes overlapped, PCA helped make clusters more compact while still retaining structure. This simplification improved interpretability without sacrificing accuracy.

---
