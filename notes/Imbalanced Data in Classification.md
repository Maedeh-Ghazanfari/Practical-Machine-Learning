In classification tasks, imbalanced datasets occur when one class significantly outnumbers the others. This can lead to a biased model that performs poorly on the minority class, even if overall accuracy seems high.

**Why It Matters**
When the target classes are imbalanced, a model may:

Learn to always predict the majority class.

Show high accuracy but perform poorly on minority class detection.

Fail in real-world applications like:

Fraud detection

Medical diagnosis

Spam filtering

**Example of Imbalance**
| Class | Count |
| ----- | ----- |
| 0     | 900   |
| 1     | 100   |

A model could just predict 0 always and still get 90% accuracy — but that’s useless.

**Techniques to Handle Imbalanced Data**

1. **Resampling the Dataset**

*Oversampling (increase minority class):

Duplicate existing samples or generate synthetic ones (e.g., SMOTE).

*Undersampling (reduce majority class):

Randomly remove samples from the majority class.

2. **Use Class Weights in the Model**

Many classifiers (like Random Forest, Logistic Regression, SVM) allow class_weight='balanced' to automatically adjust for imbalance.

