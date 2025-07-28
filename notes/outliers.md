# Outlier Detection Notes

## What Are Outliers?
Outliers are data points that differ significantly from other observations. They can be caused by variability in the data or errors.

---

## Why Detect Outliers?
- Can bias or distort statistical analyses and machine learning models.
- May indicate data quality issues.
- Important to handle appropriately (remove, transform, or keep).

---

## Types of Outliers

### 1. Univariate Outliers
- Unusual values in a single feature.
- Detected using:
  - Z-score (works well for normally distributed data)
  - Interquartile Range (IQR) method (good for skewed data)
  - Boxplots for visualization

### 2. Multivariate Outliers
- Unusual combinations of values across multiple features.
- Not always visible when looking at single features.
- Detected using algorithms that consider multiple dimensions, e.g.:
  - Isolation Forest
  - Elliptic Envelope (assumes normal distribution)
  - One-Class SVM
  - DBSCAN clustering

---

## Common Outlier Detection Methods

### Z-score
- Measures how many standard deviations a data point is from the mean.
- Suitable for normally distributed features.
- Typical threshold: |Z| > 3.

### Interquartile Range (IQR)
- Uses quartiles Q1 (25%) and Q3 (75%).
- Outliers are points below Q1 - 1.5*IQR or above Q3 + 1.5*IQR.
- Works well for skewed distributions.

### Isolation Forest
- Tree-based method isolating anomalies.
- Does not assume normality.
- Good for multivariate and skewed data.

---

## Practical Tips for Red Wine Dataset
- Features are often skewed → avoid methods assuming normality.
- Isolation Forest is recommended for multivariate outlier detection.
- Always scale features before applying Isolation Forest.

---

## References
- [Scikit-learn Isolation Forest Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.IsolationForest.html)
- [Z-score and IQR Outlier Detection](https://en.wikipedia.org/wiki/Outlier#Statistical_tests_for_outliers)

