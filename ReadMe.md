# Conclusion
The results reveal the performance of three models—Logistic Regression, Random Forest, and XGBoost—on a binary classification task, evaluated before and after hyperparameter tuning. The key metrics are precision, recall, F1-score, and macro average, focusing on the model's ability to balance performance across both classes (majority and minority).

- Before tuning, Logistic Regression achieved reasonable performance but struggled with recall for the minority class. Random Forest showed slightly better balance, but XGBoost demonstrated superior precision for the minority class at the cost of recall.
- After tuning, all models improved in terms of macro average metrics, with Logistic Regression and Random Forest achieving better recall for the minority class. XGBoost, while maintaining high precision, showed the highest macro average precision but faced challenges in recall for the minority class.

# Key Findings

1. ## **Pre-Tuning Observations**

    1. ### Logistic Regression:
        - Strong precision and F1-score for the majority class (0).
        - Relatively poor recall (0.78) for the minority class (1), resulting in a macro average recall of 0.87.

    2. ### Random Forest:
        - Better balance than Logistic Regression.
        - Recall for the minority class (0.53) was low, but overall macro average recall (0.76) was slightly higher.

    3. ### XGBoost:
        - Best macro average precision (0.91) among all models pre-tuning.
        - Low recall (0.52) for the minority class indicates difficulty in capturing minority class samples, though it maintains high precision.

2. ## **Post-Tuning Observations**

    1. ### Logistic Regression (Best Hyperparameters: `C=10`, `penalty=l2`, `solver=liblinear`):

        - Macro average precision improved to `0.82`, and recall to `0.85`.
        - F1-score for the minority class (`0.69`) showed notable improvement.
        - Balanced performance across both classes after tuning.
        - Macro F1 Score (`0.84`)

    2. ### **Random Forest (Best Hyperparameters: `max_depth=None`, `min_samples_leaf=2`, `min_samples_split=5`, `n_estimators=100`):**

        - Macro average recall increased to `0.85`, matching Logistic Regression.
        - Minority class F1-score (`0.67`) improved but was slightly lower than Logistic Regression.
        -Remains robust, with consistent accuracy and weighted averages.
        - Macro F1 Score (`0.80`)
    3. ### **XGBoost (Best Hyperparameters: learning_rate=0.2, max_depth=20, n_estimators=100):**

        - Maintained the highest macro average precision (`0.92`) but had the lowest macro average recall (`0.75`).
        - Minority class F1-score (`0.64`) remained stable, reflecting its emphasis on precision rather than recall.
        - Macro F1 Score (`0.81`)

3. ## **Overall Observations**
    - Logistic Regression achieved the best balance between precision and recall after tuning, reflected in its macro average F1-score.
    - Random Forest performed comparably to Logistic Regression but with slightly lower F1-scores for the minority class.
    - XGBoost demonstrated strong precision, making it ideal for cases where minimizing false positives is critical. However, it struggled to improve recall even after tuning.