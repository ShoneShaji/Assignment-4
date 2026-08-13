# Wine Quality Dataset Analysis Using Linear Algebra and Probability

## Overview

This project applies **Linear Algebra** and **Probability** concepts to the Wine Quality Dataset. The dataset contains physicochemical properties of wines along with their quality ratings. The analysis includes data preprocessing, vector extraction, covariance matrix computation, eigen decomposition, and probability-based analysis of wine quality distribution.

## Dataset

* **Dataset:** Wine Quality Dataset
* **Rows:** 1599
* **Columns:** 12
* **Target Variable:** Quality
* **Features Include:**

  * Fixed Acidity
  * Volatile Acidity
  * Citric Acid
  * Residual Sugar
  * Chlorides
  * Free Sulfur Dioxide
  * Total Sulfur Dioxide
  * Density
  * pH
  * Sulphates
  * Alcohol
  * Quality

## Objectives

1. Load the dataset and handle missing values.
2. Extract selected columns as vectors.
3. Compute the covariance matrix for selected features.
4. Perform eigen decomposition on the covariance matrix.
5. Analyze the distribution of wine quality scores.

## Technologies Used

* Python
* Pandas
* NumPy
* Jupyter Notebook / Anaconda

## Tasks Performed

### 1. Data Loading and Missing Value Handling

* Loaded the dataset using Pandas.
* Used `sep=';'` since the dataset is semicolon-separated.
* Replaced missing values with the mean of their respective columns.

### 2. Vector Extraction

Extracted the following features as vectors:

* Alcohol
* Citric Acid

These vectors were used for further mathematical analysis.

### 3. Covariance Matrix Calculation

Selected:

* Alcohol
* Density

Constructed a feature matrix and computed the covariance matrix using:

```python
np.cov(X.T)
```

The covariance matrix helps identify the relationship between the selected variables.

### 4. Eigen Decomposition

Performed eigen decomposition using:

```python
np.linalg.eig(cov_matrix)
```

Results obtained:

* Eigenvalues
* Eigenvectors

#### Interpretation

* The largest eigenvalue represents the direction with the highest variance.
* The corresponding eigenvector represents the first principal component.
* The second eigenvalue and eigenvector represent the next most significant direction of variation.

### 5. Wine Quality Distribution Analysis

Calculated the frequency of each quality score using:

```python
df['quality'].value_counts()
```

#### Findings

* Quality score **5** is the most common in the dataset.
* Quality scores **5** and **6** account for the majority of wines.
* Extremely low-quality and high-quality wines are comparatively rare.

## Key Observations

* Most wines belong to the medium-quality range.
* Alcohol and density exhibit a measurable relationship captured by the covariance matrix.
* The first principal component explains most of the variance in the selected features.
* The dataset is not evenly distributed across quality scores.

## Conclusion

This project demonstrates how Linear Algebra techniques such as covariance matrices, eigenvalues, and eigenvectors can be applied to real-world datasets. Additionally, probability concepts help understand the distribution of wine quality scores. Together, these methods provide valuable insights into the characteristics and quality of wines in the dataset.
