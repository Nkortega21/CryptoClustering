# CryptoClustering
UCI Data Analyst Module 19 - Unsupervised Learning

# Cryptocurrency Clustering with K-Means and PCA

## Overview

This project involves clustering cryptocurrencies using K-Means and Principal Component Analysis (PCA). The goal is to analyze the relationships between different cryptocurrencies based on their market data, and to explore the impact of using PCA to reduce the number of features before performing K-Means clustering.

## Questions to Answer

1. **What is the best value for k when using the scaled DataFrame?**
  -  4 because it is the section of the graph where k begins to elbow.
2. **What is the total explained variance of the three principal components?**
  - ~89.5% can be explained with these prinicipal components
3. **What is the best value for k when using the scaled PCA DataFrame? Does it differ from the original?**
  - The best value for k is still 4. The only difference is that the inertia has a lower value at 4
4. **What is the impact of using fewer features to cluster the data using K-Means?**
  - Using fewer clusters could allow for the K-Means to be more distinguished.

## Steps

### 1. Prepare the Data

- Normalize the data using `StandardScaler()` from scikit-learn to ensure all features are on a similar scale.
- Create a new DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
- Display the first five rows of the scaled DataFrame for verification.

### 2. Find the Best Value for k Using the Scaled DataFrame

- Use the elbow method to determine the best value for k. This involves:
  - Creating a list of k values ranging from 1 to 11.
  - Computing the inertia for each k value.
  - Plotting the inertia values to visually identify the optimal k.

### 3. Cluster Cryptocurrencies with K-Means Using the Scaled DataFrame

- Initialize the K-Means model with the best k value identified from the elbow method.
- Fit the K-Means model using the scaled data and predict the clusters.
- Create a copy of the scaled DataFrame and add a new column with the predicted clusters.
- Visualize the clusters by plotting a scatter plot with:
  - X-axis: "price_change_percentage_24h"
  - Y-axis: "price_change_percentage_7d"
  - Color the points based on the predicted clusters, with the cryptocurrency name shown on hover.

### 4. Optimize Clusters with Principal Component Analysis (PCA)

- Perform PCA to reduce the features to three principal components.
- Retrieve the explained variance to determine how much information can be attributed to each principal component.
- Create a new DataFrame with the scaled PCA data and set the "coin_id" index.
- Display the first five rows of the PCA DataFrame.

### 5. Find the Best Value for k Using the PCA DataFrame

- Repeat the elbow method on the scaled PCA DataFrame, using the same k-value range from 1 to 11.
- Plot the inertia values to identify the optimal k for the PCA data.
- Compare the best k value from the scaled data with that from the PCA data.

### 6. Cluster Cryptocurrencies with K-Means Using the PCA DataFrame

- Initialize the K-Means model with the best k value from the PCA data.
- Fit the K-Means model using the scaled PCA data and predict the clusters.
- Create a copy of the scaled PCA DataFrame and add a new column with the predicted clusters.
- Visualize the clusters by plotting a scatter plot with:
  - X-axis: "PC1"
  - Y-axis: "PC2"
  - Color the points based on the predicted clusters, with the cryptocurrency name shown on hover.

### 7. Visualize and Compare the Results

- Create composite plots comparing:
  - The elbow curve from the original scaled data with the one from the PCA data.
  - The cryptocurrency clusters from the scaled data with those from the PCA data.
- Analyze the impact of using fewer features (from PCA) to cluster the data with K-Means.

### 8. Code Comments and Documentation

Ensure that all code is well-commented with concise and relevant notes to help other developers understand the logic and purpose of each step.
