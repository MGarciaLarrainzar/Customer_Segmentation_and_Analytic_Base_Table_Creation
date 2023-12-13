Data Import and Preprocessing:

Import the tables "customers" and "income_for_address."
Infer column types from data files to prevent potential issues later.
Creating Column for Average Income:

Generate a new column named "income_avg" in the "customers" table.
Match each customer's "address" to the corresponding "income_for_address" table to populate the "income_avg" based on the average income in their location.
Handling Skewed Income Data:

Replace the existing "income" column in "customers" with a new column named "log_income," calculated as the logarithm of the income.
Removing Outliers and Imputing Missing Values:

Remove rows where the number of cars is 5 or more, considering them outliers.
Impute missing values in columns (excluding "age") with mean imputation. For "age," fill missing values with a fixed value of 70 due to privacy or non-disclosure concerns.
Identifying Highly Correlated Column:

Determine the column in "customers" that exhibits the highest Pearson correlation with "cardtenure" (excluding "cardtenure" itself). This column will be referred to as the "bad column."
Creating the Analytic Base Table (ABT) for Clustering:

Form the ABT, excluding outliers and the identified "bad column," "address," "Accept" (label), "custid," and "income" columns.
Perform rescaling using avg-std rescaling, including the "log_income" column.
K-means Clustering:

Apply K-means clustering with k=3 on the ABT, using different seeds based on group assignment.
Set parameters for outlier detection, min-cluster size, and thresholds to identify and remove outliers.
Analysis of Clustering Solution:

Calculate the average of the variable "Accept" in the smallest cluster.
Creating Dataset with Cluster Identity:

Generate a new dataset similar to the ABT but including a column specifying the cluster identity for each row.
Sort the rows by "custid" in increasing order.
