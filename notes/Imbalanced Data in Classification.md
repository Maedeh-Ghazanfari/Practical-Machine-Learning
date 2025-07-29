# 🧪 Handling Imbalanced Classes in Machine Learning

In classification tasks, imbalanced datasets occur when one class significantly outnumbers the others. This can lead to a biased model that performs poorly on the minority class, even if overall accuracy seems high.

## **Why It Matters?**

When the target classes are imbalanced, a model may Learn always to predict the majority class. Shows high accuracy but performs poorly on minority class detection. Fail in real-world applications such as fraud detection, Medical diagnosis, and Spam filtering.

**Example of Imbalance**
| Class | Count |
| ----- | ----- |
| 0     | 900   |
| 1     | 100   |

A model could just predict 0 always and still get 90% accuracy — but that’s useless.

## **Techniques to Handle Imbalanced Data**

**1. Resampling the Dataset**

* Oversampling (increase minority class): Duplicate existing samples or generate synthetic ones (e.g., SMOTE).
# SMOTE:

Unlike simple oversampling (duplicating existing points), SMOTE creates new, realistic data points by interpolating between existing minority class samples.

# How does it work?

1. For each minority class sample, find its k nearest neighbors (usually k=5).

2. Randomly pick one neighbor.

3. Generate a synthetic sample somewhere on the line segment joining the original sample and the neighbor.

4. Repeat until the minority class is upsampled to the desired size.

* Undersampling (reduce majority class): Randomly remove samples from the majority class.

 **2. Use Class Weights in the Model**

Many classifiers (like Random Forest, Logistic Regression, SVM) allow class_weight='balanced' to automatically adjust for imbalance. It tells the model, it's okay if you get the majority class wrong sometimes, but it's more costly to misclassify the rare classes. During model training, the **loss function** considers these weights.
Errors on rare classes are penalized more, so the model learns to focus on them too.

