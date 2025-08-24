Data preprocessing is arguably the most critical stage in any data analysis or machine learning project. The principle of "Garbage In, Garbage Out" (GIGO) perfectly applies here. Without rigorous preprocessing:
Analysis would be inaccurate: Calculating the average funding amount would fail or give wrong results if the data isn't a clean numeric type.
Models would be unreliable: A machine learning model trained on messy data with missing values and incorrect types will produce poor and untrustworthy predictions.
Insights would be flawed: We might draw incorrect conclusions, for instance, by thinking a category is unpopular when in reality its name is just misspelled in various ways (e.g., 'Fintech', 'fintech', 'Fin-tech').

In a real-world scenario, clean and well-prepared data is the foundation upon which all trustworthy business decisions are built. This exercise shows that raw data is rarely perfect and that a data scientist's first duty is to bring order and structure to it.

Based on the initial exploration of the dataset:

The dataset contains 26 entries and 11 columns.

Several columns have missing values:

Effective date : 20 missing values

Financing Type : 18 missing values

Financing Type Normalized : 18 missing values

Investors : 13 missing values

Investors Count : 13 missing values

The data types are mostly object (strings), with Amount Normalized as int64 and Investors

Count as float64 .

The Amount column contains values with different currencies and formats, while Amount Normalized

provides a standardized numerical representation of the funding amount.

The numerical columns ( Investors Count and Amount Normalized ) have a wide range of values,

indicated by the standard deviation and the difference between minimum and maximum values in the

statistical summary. The median Amount Normalized is significantly lower than the mean, suggesting the

presence of some large outliers.

df.info()

<class 'pandas.core.frame.DataFrame'>

RangeIndex: 26 entries, 0 to 25

Data columns (total 11 columns):

 # Column Non-Null Count Dtype 

--- ------ -------------- ----- 

 0 Website Domain 26 non-null object 

 1 Effective date 6 non-null object 

 2 Found At 26 non-null object 

 3 Financing Type 8 non-null object 

 4 Financing Type Normalized 8 non-null object 

 5 Categories 26 non-null object 

 6 Investors 13 non-null object 

 7 Investors Count 13 non-null float64

 8 Amount 26 non-null object 

 9 Amount Normalized 26 non-null int64 

 10 Source Urls 26 non-null object 

dtypes: float64(1), int64(1), object(9)

memory usage: 2.4+ KB
