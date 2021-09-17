#### Link for the repo - [https://github.com/ishara28/ML-Project-Drivendata](https://github.com/ishara28/ML-Project-Drivendata)

### **Data Cleaning**

- Concatenated training values and training labels and as training data.
- Concatenated training data with testing data as df
- Explored the features and dropped unwanted features
  - Checked for missing values and there were missing values
  - Checked what are the target classes
- There are some columns with similar data. Cleared and rearrange them first
  - &#39;scheme management&#39; &amp; &#39;management&#39;
    - Both columns have the same kind of data. But in the &#39;scheme\_management&#39; column, there are 3877 missing values. So it is better to keep &#39;management&#39; and drop the &#39;scheme\_management&#39;
  - &#39;quantity&#39; and &#39;quantity\_group&#39;
    - Both above 2 columns (&#39;quantity&#39; &amp; &#39;quantity\_group&#39;) have same values. So, we can drop one column.
    - Dropped quantity group
  - &#39;source&#39; and &#39;source\_types&#39;
    - Both columns have the same kind of values and &#39;source&#39; has more data. So drop the &#39;source\_type&#39; column.
  - &#39;water\_quality&#39; and &#39;quality\_group&#39;
    - We can see that both columns have the same kind of data and water\_quality&#39; has more values. So, drop the &#39;quality\_group&#39;
  - &#39;payment&#39; and &#39;payment\_types&#39;
    - We can see that both have the same values. So we can drop one. I dropped &#39;paymenent\_type&#39;
  - &#39;extraction\_type&#39; and &#39;extraction\_type\_group&#39;
    - We can see that both columns have the same kind of values and &#39;extraction\_type&#39; has more unique values. So I dropped the &#39;extraction\_type\_group&#39;
  - &#39;waterpoint\_type&#39; and &#39;waterpoint\_type\_group&#39;
    - We can see that both columns contain the same kind of data, but &#39;waterpoint\_type&#39; contains more unique data. So, I dropped &#39;waterpoint\_type\_group&#39;
- Filling missing values
  - &#39;installer&#39; column
    - There are many spelling mistakes and errors in recording there like,

      - District Water Department , District water depar, Distric Water Department

      - Central Government , Cental Governmen
    - The same value has been recorded in different ways
      - RC CHURCH, RC Church
    - Replaced those kinds of values with a suitable value.
    - There were many unique values in the Installer column
    - Most of them were with very low frequency.
    - Selected which are less than 300 and categorized them as &#39;others&#39;
    - Dropped &#39;installer&#39; column and add a new column as &#39;installer\_category&#39;
  - &#39;funder&#39; column
    - Same as in &#39;installer&#39;, here are also categories with very low counts.
    - Got the first 20 categories from there and all the others were categorized as &#39;others&#39;
    - Dropped &#39;funder&#39; column and added &#39;funder\_categories&#39;
  - &#39;public\_meeting&#39; column
    - Most values were True
    - Filled missing values with True
  - &#39;permit&#39; column
    - Most values were True
    - Filled missing values with True
- &#39;recorded\_by&#39; column
  - This has only one value. So no effect from that column. Dropped it.
- &#39;date\_recorded&#39; column
  - Most of the data were recorded in nearest years each other (like 2 years) we can ignore it and drop the column
- &#39;num\_private&#39; column
  - We can see that most values have a value of &quot;0&quot;. We can drop this column
- Label encoded all the categorical columns.
- Finally, this cleaned and refined data are saved as &#39;Refined\_data.csv

### **Preprocessing**

- Handled missing values as described above.
- Used Standard scaling for normalization.
- Used label encoding for categorical features.

### **Feature Selection**

- For the feature selection, I used &#39;Sequential Feature Selection&#39; (SFS)
- Done SFS with Random Forest
- Selected features with max score

### **Post-processing approaches**

- Done Feature Importance to check what are the most important features for the classification.

### **Model Evaluation**

- Selected models
  - KNN classification
  - XGBoost
  - Catboost
  - Random Forest
- Random Forest gave the best accuracy.
- Created the submission file with the predictions by Random Forest Model.
