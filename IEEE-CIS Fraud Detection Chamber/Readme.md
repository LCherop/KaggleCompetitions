## Competition Details
The competition details can be found [here](https://www.kaggle.com/competitions/ieee-fraud-detection/overview)
## My approach
### Understanding the Beast:
+ Grasped the competition's goal and explored the datasets.
+ Prepped with pandas, NumPy, and scikit-learn for data wrangling.
+ Performed initial data exploration (describe, info, shape) to get a feel for the data.

### Memory Maneuvers (Colab-Specific):
+ Implemented a function to shrink the datasets for efficient Colab use.

### Data Cleaning: Individual Scrubbing
+ Cleaned each dataset separately to catch specific issues.
+ Removed columns lacking transaction ID info (consistency is key!).
+ Dropped columns with excessive missing values (>70%).
+ Imputed missing numerical values (method to be documented later).

### Categorical Data Wrangling (Current Focus):
+ Identified features with varying cardinality (number of unique values).
+ Considering model-based imputation (decision trees/random forests) for missing values.

### Planned Techniques for Categorical Data:
+ Encoding: Exploring PCA/ICA for high-cardinality features to avoid memory bloat from one-hot encoding.
+ Feature Engineering: May create new features to boost model performance.

### Next Steps:
+ Encoding the data
+ Model Selection & Building
+ Model evaluation
## Lessons Learned
### Different Types of Imputation Methods
1. Mode Imputation:

    This is a simple and intuitive technique. You replace missing values with the most frequent category in the column.
    It's easy to implement and works well when the missing data is random and the mode is a good representative of the missing values.
    However, it can be misleading if the missingness is not random, or if there are multiple frequent categories.

2. Category Encoding and Imputation with Numerical Techniques:

    Convert your categorical data to numerical representations (e.g., one-hot encoding).
    Use standard numerical imputation techniques like mean/median imputation or more sophisticated methods like K-Nearest Neighbors (KNN) imputation.
    Finally, convert the imputed numerical values back to categorical labels.

3. K-Nearest Neighbors (KNN) Imputation:

    This approach identifies similar rows based on the available features and uses the most frequent category among the K nearest neighbors to fill in the missing value.
    It can be more accurate than mode imputation when dealing with non-random missingness. However, KNN imputation can be computationally expensive for large datasets.

4. Rule-Based Imputation:

    If you have domain knowledge about the relationships between features, you can create custom rules to impute missing values based on other features in the dataset.
    This method can be very effective when the rules are well-defined, but it requires specific knowledge about the data and can be time-consuming to implement.

5. Model-Based Imputation:

    Train a separate model (e.g., decision tree) to predict missing values based on other features in the dataset.
    This can be a powerful approach, especially for complex relationships, but it requires careful model training and validation.

Choosing the Right Technique:
+ Data Availability: Some techniques like KNN or model-based imputation require more data compared to simpler methods like mode imputation.
+ Missingness Pattern: Consider whether the missingness is random or non-random. KNN or rule-based might be better for non-random missingness.
+ Computational Resources: Techniques like KNN or model-based imputation can be computationally expensive.
