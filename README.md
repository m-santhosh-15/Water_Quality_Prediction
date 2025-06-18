# Water_Quality_Prediction
# week-1

1. Importing Libraries
The first cell imports all the necessary Python libraries.

pandas as pd: Used for data manipulation and analysis, especially with DataFrames.
numpy as np: Provides support for large, multi-dimensional arrays and mathematical functions.
sklearn.multioutput.MultiOutputRegressor: This is a meta-estimator that allows a single estimator to be used to predict multiple target variables. In this case, it will wrap the RandomForestRegressor to predict all the specified water quality parameters simultaneously.
sklearn.ensemble.RandomForestRegressor: A powerful ensemble learning method for regression tasks. It builds multiple decision trees and merges their predictions to get a more accurate and stable prediction.
sklearn.model_selection.train_test_split: Used to split arrays or matrices into random train and test subsets. This is crucial for evaluating the model's performance on unseen data.
sklearn.metrics.mean_absolute_error: A regression loss metric that measures the average magnitude of the errors in a set of predictions, without considering their direction.
sklearn.metrics.r2_score: The R-squared (R 
2
 ) score, also known as the coefficient of determination, provides a measure of how well observed outcomes are replicated by the model, based on the proportion of total variation of outcomes explained by the model.
2. Loading the Dataset

Python

df = pd.read_csv(r'Water_Quality_Prediction_dataset.csv', sep=';')
This line reads the data from the specified CSV file into a pandas DataFrame called df. The sep=';' argument indicates that the values in the CSV are separated by semicolons, not the default comma.

3. Data Information and Shape

Python

df.info()
df.shape
df.info(): This method prints a concise summary of the DataFrame. It includes the index dtype and columns, non-null values, and memory usage. This is useful for quickly seeing data types and identifying columns with missing values.
df.shape: Returns a tuple representing the dimensionality of the DataFrame (number of rows, number of columns).
4. Descriptive Statistics

Python

df.describe().T
df.describe() generates descriptive statistics that summarize the central tendency, dispersion, and shape of a dataset's distribution for numerical columns. Applying .T (transpose) makes the output more readable by swapping rows and columns, displaying statistics for each column as a row.

5. Checking for Missing Values

Python

df.isnull().sum()
This code calculates the number of missing (NaN) values in each column of the DataFrame. This is a critical step in data preprocessing, as missing values can affect model performance.

6. Date Column Transformation and Feature Engineering

Python

df['date'] = pd.to_datetime(df['date'], format='%d.%m.%Y')
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['date'] = pd.to_datetime(df['date'], format='%d.%m.%Y'): Converts the 'date' column from an object (string) data type to a datetime object. The format argument ensures correct parsing of the date string (e.g., '17.02.2000').
df['year'] = df['date'].dt.year: Extracts the year from the datetime 'date' column and creates a new 'year' column.
df['month'] = df['date'].dt.month: Extracts the month from the datetime 'date' column and creates a new 'month' column. These newly created 'year' and 'month' columns can be valuable features for a time-series-aware model.
7. Defining Pollutants (Target Variables)

Python

pollutants = ['O2', 'NO3', 'NO2', 'SO4', 'PO4', 'CL']
This line defines a list named pollutants containing the names of the water quality parameters that the model aims to predict. These will serve as the multiple target variables for the MultiOutputRegressor.
