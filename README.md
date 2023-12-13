1. **_Data Import and Preprocessing_**:

Import the tables "customers" and "income_for_address."
Infer column types from data files to prevent potential issues later.

2. **_Creating Column for Average Income_**:

Generate a new column named "income_avg" in the "customers" table.
Match each customer's "address" to the corresponding "income_for_address" table to populate the "income_avg" based on the average income in their location.

3. **_Handling Skewed Income Data_**:

Replace the existing "income" column in "customers" with a new column named "log_income," calculated as the logarithm of the income.

4. **_Removing Outliers and Imputing Missing Values_**:

Remove rows where the number of cars is 5 or more, considering them outliers.
Impute missing values in columns (excluding "age") with mean imputation. For "age," fill missing values with a fixed value of 70 due to privacy or non-disclosure concerns.

5. **_Identifying Highly Correlated Column_**:

Determine the column in "customers" that exhibits the highest Pearson correlation with "cardtenure" (excluding "cardtenure" itself). This column will be referred to as the "bad column."

6. **_Creating the Analytic Base Table (ABT) for Clustering_**:

Form the ABT, excluding outliers and the identified "bad column," "address," "Accept" (label), "custid," and "income" columns.
Perform rescaling using avg-std rescaling, including the "log_income" column.

7. **_K-means Clustering_**:

Apply K-means clustering with k=3 on the ABT, using different seeds based on group assignment.
Set parameters for outlier detection, min-cluster size, and thresholds to identify and remove outliers.

8. **_Analysis of Clustering Solution_**:

Calculate the average of the variable "Accept" in the smallest cluster.

9. **_Creating Dataset with Cluster Identity_**:

Generate a new dataset similar to the ABT but including a column specifying the cluster identity for each row.
Sort the rows by "custid" in increasing order.
