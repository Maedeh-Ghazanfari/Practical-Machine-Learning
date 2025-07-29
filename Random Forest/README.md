# 🟢 Random Forest Classifier – Wine Quality Prediction

This project explores the use of the Random Forest algorithm for predicting wine quality. It includes preprocessing steps, handling class imbalance, outlier detection, hyperparameter tuning, and thorough model evaluation.

---

## 📁 Dataset

- **Source**: Wine Quality dataset from [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/wine+quality)
- **Target variable**: `quality` (integer score from 0 to 10)

---

## 📌 Objective

To build a Random Forest model capable of predicting wine quality, taking into account data imbalance, outliers, and hyperparameter tuning.

---

## ⚙️ Steps Implemented

1. **Data Preprocessing**
   - Removed the `quality` column to isolate features
   - Applied train-test split (80-20)
   - SMOTE applied *after* splitting to balance the training set

2. **Outlier Detection**
   - Used **Isolation Forest** to detect and remove outliers from the training data
   - Helped reduce the effect of extreme values on the model

3. **Modeling**
   - Used `RandomForestClassifier` from scikit-learn
   - Applied `class_weight='balanced'` to help handle class imbalance

4. **Hyperparameter Tuning**
   - Performed `GridSearchCV` using 5-fold cross-validation
   - Parameters tuned:
     - `n_estimators`
     - `max_depth`
     - `min_samples_split`
     - `max_features`
     - `class_weight`

5. **Feature Importance**
   - Analyzed feature importances to assess their contribution
   - Considered dropping low-importance features (did not improve performance)

6. **Evaluation**
   - Evaluated using classification report (precision, recall, F1)
   - Noted high training accuracy (~80%) vs. low test accuracy (~53%)

---

## 🧠 Observations

- Despite tuning and outlier removal, the model still shows signs of **overfitting**
- **Class imbalance** and **limited signal** in features could be major causes
- Some features had very low importance, but dropping them didn’t help much

---

## ❗ Challenges

- **Severe class imbalance**: Some quality classes have very few samples
- **Model bias**: Classifier still favors majority classes
- **Overfitting**: Good training accuracy but poor generalization to the test set

---

## 🔄 Next Steps

- Try **XGBoos**
