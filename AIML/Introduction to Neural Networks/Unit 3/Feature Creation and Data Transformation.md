## Overview
Feature engineering is the process of transforming raw data into meaningful features that improve the performance of machine learning models. It involves creating, modifying, and selecting variables to capture underlying patterns.

---

## Steps in Feature Engineering
1. Feature Creation:
	-  It involves creating new variables which will be most helpful for our model. This can be adding or removing some features.
	- Ex: Extracting the day of the week from a date

2. **Transformations**
   - Is simply a function that transforms features from one representation to another (Ex: Log transformation, Min-Max scaling, Encoding, Standardization etc.).

3. **Feature Extraction**
   - Is about extracting/deriving information from the original features set to create a new features subspace
   - Encode categorical variables.
   - Apply domain knowledge to derive meaningful attributes.

4. **Exploratory Data Analysis**
   - Create hypothesis and find new patterns in data
   
5. **Benchmark**
- Compares the model developed against most user friendly, dependable, transparent and interpretable model.

6. **Feature Selection**
   - Remove irrelevant or redundant features.
   - Use statistical tests, correlation analysis, or model-based importance.


---

## Techniques for Feature Engineering

### 1. Encoding
- **One-Hot Encoding**: Convert categorical values into binary vectors.
	![[Pasted image 20251118181114.png|300]]
- **Label Encoding**: Assign integer values to categories.
	![[Pasted image 20251118181021.png|300]]

### 2. Scaling and Normalization
- **Min-Max Scaling(Normalization)**: Scale values to a fixed range (e.g., [0,1]).
$$X_{norm} = \frac{(X - X_{min})}{(X_{max} - X_{min})}$$
- **Standardization (Z-score)**: Center values around mean with unit variance.
$$Z=\frac{x-\mu}{\sigma}$$

### 3. Outliers Handling
 - Removal: Outlier-containing entries are deleted from the distribution. However, if there are outliers across numerous variables, this strategy may result in a big chunk of the datasheet being missed.
- Replacing values: Alternatively, the outliers could be handled as missing values and replaced with suitable imputation.
- Capping: Using an arbitrary value or a value from a variable distribution to replace the maximum and minimum values.

### 4. Imputation

1. **Variable Deletion (numeric & categorical)**  
   Drop variables with high missing values (≥60%) if they are less important.

2. **Mean/Median Imputation (numeric only)**  
   Replace missing values with the mean or median of observed data.

3. **Mode Imputation (numeric & categorical)**  
   Fill missing values with the most frequently occurring value.

4. **Assigning New Category (categorical only)**  
   Introduce a placeholder category (e.g., "Unknown") for missing entries.

5. **Predict Missing Values (numeric & categorical)**  
   Use regression or classification models to estimate missing values based on correlations with other features.

### 5. Transformation
- **Log Transformation**: Reduce skewness in distributions. Log values of the column are taken and these are utilized
as column values in this transform.
