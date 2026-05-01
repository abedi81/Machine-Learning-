# EV Charging Behavior Segmentation: Clustering Analysis

## Overview

This project applies unsupervised machine learning techniques to analyze and segment electric vehicle (EV) charging behavior.

The goal is to identify distinct groups of users based on how they charge their vehicles, including battery levels, energy consumption, charging duration, and usage patterns. These insights help understand demand patterns and support optimization of charging infrastructure.

---

## Methodology

The dataset contains detailed EV charging session records, including:

- Battery state of charge (start and end)  
- Energy consumption and charging duration  
- Charging cost and distance traveled  
- Environmental factors (temperature)  
- User context (user type, location, time of day)  

### Data Preprocessing

- Missing values were handled  
- Skewed variables (duration, cost, distance) were transformed  
- Categorical variables were encoded  
- Non-informative identifiers were removed  
- All numerical features were scaled  

 This ensures consistency and prevents bias in clustering.

---

## Dimensionality Reduction (PCA)

Principal Component Analysis was used to simplify the dataset:

- **PC1:** Starting battery level  
- **PC2:** Energy consumption  

 These two components capture the main behavioral patterns and allow clear visualization of clusters.

---

## Clustering Models

Several clustering algorithms were applied and compared:

### 1. K-Means
- Produced balanced and interpretable clusters  
- Selected as the final model  

### 2. Gaussian Mixture Model (GMM)
- Captures probabilistic cluster membership  
- Performs similarly to K-Means  

### 3. DBSCAN
- Not suitable due to lack of dense clusters  
- Groups most users into one cluster  

### 4. Hierarchical Clustering
- Produces highly imbalanced clusters  
- Not meaningful for segmentation  

---

## Cluster Interpretation

The analysis identifies four distinct charging behaviors:

### Cluster 0: Low Battery, Heavy Charging
- Arrive with low battery  
- Consume large amounts of energy  
- Long charging sessions  

This group behaving like High dependency on charging infrastructure  

---

### Cluster 1: Low Battery, Light Charging
- Start with low battery  
- Perform small top-ups  

This group is Short-stop or opportunistic users  

---

### Cluster 2: High Battery, Heavy Charging
- Start with high battery  
- Still consume large energy  

This group is Likely long-distance travelers  

---

### Cluster 3: High Battery, Light Charging
- Arrive with high battery  
- Small charging amounts  

This group is Routine or convenience charging  

---

## Key Findings

- Charging behavior is driven mainly by:
  - Starting battery level  
  - Energy consumption  

- Four clear behavioral segments exist  
- K-Means and GMM produce consistent and reliable clusters  
- Not all models with strong metrics produce meaningful results  

---

## Business Insight

- EV charging demand is highly heterogeneous  
- Heavy users create peak demand and infrastructure pressure  
- Light users provide steady, flexible demand  

### Practical Implications:

- Deploy fast chargers for heavy users  
- Use Level 2 chargers for light users  
- Apply dynamic pricing to manage demand  
- Optimize station placement and capacity  

 This leads to better resource allocation and reduced congestion.

---

## Skills Demonstrated

- Unsupervised learning (clustering)  
- K-Means, GMM, DBSCAN, Hierarchical clustering  
- Dimensionality reduction (PCA)  
- Feature engineering and preprocessing  
- Model evaluation and comparison  
- Translating data insights into business strategy  
