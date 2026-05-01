# Credit Card Customer Segmentation: Clustering Analysis

## Overview

This project applies unsupervised machine learning techniques to segment credit card customers based on their financial behavior.

The goal is to identify meaningful customer groups using patterns in spending, borrowing, and repayment behavior, enabling better understanding of customer types and supporting data-driven decision-making.

---

## Methodology

The dataset contains customer-level financial activity, including:

- Spending behavior (purchases, transaction frequency)  
- Credit usage (balance, credit limit)  
- Cash usage (cash advances)  
- Payment behavior (payments, minimum payments, full payment ratio)  

### Data Preprocessing

To ensure comparability and model performance:

- Missing values were handled  
- Outliers were treated  
- Skewed features were transformed (log / Box-Cox)  
- All variables were standardized  

 This ensures all features contribute equally to clustering.

---

## Estimation Approaches

Multiple clustering algorithms were applied and compared:

### 1. K-Means Clustering

- Partitions customers into distinct groups  
- Produces balanced and interpretable clusters  
- Selected as the final model  

---

### 2. Gaussian Mixture Model (GMM)

- Allows soft clustering (probabilistic membership)  
- Captures overlapping customer behavior  
- Slightly less interpretable in this dataset  

---

### 3. Hierarchical Clustering

- Builds clusters step-by-step  
- Produced imbalanced groupings  

---

### 4. DBSCAN

- Density-based clustering  
- Grouped most customers into one cluster with few outliers  
- Not suitable for this dataset due to lack of density variation  

---

## Dimensionality Reduction (PCA)

Principal Component Analysis (PCA) was used for:

- Visualization of clusters  
- Reducing dimensionality  

### Key Components:

- **PC1:** Spending and purchasing activity  
- **PC2:** Debt and balance behavior  
- **PC3:** Credit capacity and repayment discipline  

 First two components explain ~55% of total variation.

---

## Cluster Interpretation

### Cluster 0: High-Value Customers
- High spending and transaction activity  
- Strong repayment behavior  
- High balance and credit limits  

we can call this group  **Premium, low-risk, high-profit customers**

---

### Cluster 1: Cash-Dependent / Risky Users
- High cash advance usage  
- High balances and minimum payments  
- Low full repayment rates  

We will call this group **High-risk, credit-dependent customers**

---

### Cluster 2: Inactive Customers
- Very low activity across all features  
- Minimal spending and repayment  

We will call this group **Low engagement, low revenue customers**

---

### Cluster 3: Moderate Active Users
- Regular but moderate usage  
- Reasonable repayment behavior  

We will Call this group **Stable, medium-value customers**

---

## Model Evaluation

Models were evaluated using:

- Silhouette Score  
- Davies–Bouldin Index  
- Calinski–Harabasz Index  

### Key Insight:

- Some models showed strong metrics but produced **unbalanced clusters**  
- K-Means provided the best trade-off between:
  - Statistical performance  
  - Practical interpretability  

---

## Key Findings

- Customer behavior can be segmented into 4 meaningful groups  
- K-Means provides the most actionable segmentation  
- PCA confirms clear separation between clusters  
- Not all high-scoring models are useful in practice  

---

## Business Insight

- High-value customers can be targeted for premium services  
- Risky users require credit monitoring and intervention  
- Inactive users can be targeted with engagement campaigns  
- Moderate users can be encouraged to increase spending  
 

---

## Skills Demonstrated

- Unsupervised learning (clustering)  
- K-Means, GMM, DBSCAN, Hierarchical clustering  
- Dimensionality reduction (PCA)  
- Feature engineering and preprocessing  
- Model evaluation and comparison  
- Translating data into business insights  
