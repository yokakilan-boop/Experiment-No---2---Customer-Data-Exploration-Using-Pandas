# DSWP-Experiment-2-Customer-Data-Exploration-Using-Pandas

## Aim
To create a sample customer dataset and perform data exploration, filtering, sorting, grouping, and basic statistical analytics using Pandas functions in Python.

## Algorithm

1. **Start** the program.
2. **Import Library**: Import the `pandas` library as `pd` for tabular data manipulation and analysis.
3. **Initialize Dataset**: Create a Python dictionary `data` containing customer attributes (`Customer_ID`, `Customer_Name`, `Region`, `Age`, `Annual_Income`, `Spending_Score`, `Loyalty_Years`).
4. **Construct DataFrame**: Convert the dictionary into a structured Pandas DataFrame `df` using `pd.DataFrame(data)` and print the dataset.
5. **Inspect Structure & Summary**:
   * Display dataset dimensions (`df.shape`), column names (`df.columns`), data types and null counts (`df.info()`), and descriptive statistics (`df.describe()`).
   * Display the first 3 records (`df.head(3)`) and last 3 records (`df.tail(3)`).
6. **Sort & Filter Records**:
   * Sort customers in descending order of `Annual_Income` using `df.sort_values()`.
   * Filter high-income customers where `Annual_Income > 70000`.
7. **Perform Group-Wise & Frequency Analysis**:
   * Group customers by `Region` and calculate regional averages for `Annual_Income` and `Spending_Score` using `df.groupby().mean()`.
   * Count customer distribution across each region using `df["Region"].value_counts()`.
8. **Compute Overall Metrics & Top Performer**:
   * Identify the customer record with the highest `Spending_Score` using `df["Spending_Score"].idxmax()` and `df.loc[]`.
   * Calculate overall mean `Annual_Income` and mean `Spending_Score`.
9. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Data Creation** | `pd.DataFrame()` | Converts a Python dictionary into a 2D labeled tabular DataFrame |
| **Structural Inspection** | `df.shape`, `df.columns` | Retrieves dimensions `(rows, columns)` and column labels |
| | `df.info()`, `df.describe()` | Summarizes column data types, memory usage, and descriptive statistics |
| | `df.head(n)`, `df.tail(n)` | Views the first `n` and last `n` rows of the dataset |
| **Sorting & Filtering** | `df.sort_values()` | Orders records by `Annual_Income` in descending order |
| | Boolean Indexing (`df[...]`) | Filters customers with `Annual_Income > 70000` |
| **Grouping & Aggregation** | `df.groupby().mean()` | Aggregates mean income and spending score per `Region` |
| | `df["Region"].value_counts()` | Counts occurrences of customers in each region |
| | `idxmax()`, `df.loc[]`, `.mean()` | Locates the top spender row and computes dataset-wide averages |

## Program
## Input 1
```
# Customer Data Exploration using Pandas
import pandas as pd

# Step 1: Create a sample customer dataset
data = {
    "Customer_ID": [101, 102, 103, 104, 105, 106, 107, 108],
    "Customer_Name": ["Anita", "Rajesh", "Priya", "Vikram", "Divya", "Manoj", "Sita", "Amit"],
    "Region": ["North", "South", "East", "West", "North", "South", "East", "West"],
    "Age": [25, 32, 41, 29, 35, 45, 28, 40],
    "Annual_Income": [55000, 72000, 61000, 48000, 85000, 90000, 64000, 58000],
    "Spending_Score": [78, 62, 45, 88, 92, 55, 70, 60],
    "Loyalty_Years": [2, 5, 4, 3, 6, 7, 3, 4]
}
#Customer Data Exploration using Pandas

# Step 2: Convert to a Pandas DataFrame
df = pd.DataFrame(data)
print("---- CUSTOMER DATASET ----")
print(df)
```
## Output 1
```
---- CUSTOMER DATASET ----
   Customer_ID Customer_Name Region  Age  Annual_Income  Spending_Score  \
0          101         Anita  North   25          55000              78   
1          102        Rajesh  South   32          72000              62   
2          103         Priya   East   41          61000              45   
3          104        Vikram   West   29          48000              88   
4          105         Divya  North   35          85000              92   
5          106         Manoj  South   45          90000              55   
6          107          Sita   East   28          64000              70   
7          108          Amit   West   40          58000              60   

   Loyalty_Years  
0              2  
1              5  
2              4  
3              3  
4              6  
5              7  
6              3  
7              4  
```
## Input 2
```
# Step 3: Basic exploration
print("\nShape of Dataset:", df.shape)
print("Columns:", df.columns.tolist())
print("\n---- Dataset Info ----")
df.info()
print("\n---- Summary Statistics ----")
print(df.describe())
```
## Output 2
```
Shape of Dataset: (8, 7)
Columns: ['Customer_ID', 'Customer_Name', 'Region', 'Age', 'Annual_Income', 'Spending_Score', 'Loyalty_Years']
```
## Input 3
```
# Step 4: Display first and last few records
print("\nFirst 3 Records:\n", df.head(3))
print("\nLast 3 Records:\n", df.tail(3))

```
## Output 3
```
First 3 Records:
    Customer_ID Customer_Name Region  Age  Annual_Income  Spending_Score  \
0          101         Anita  North   25          55000              78   
1          102        Rajesh  South   32          72000              62   
2          103         Priya   East   41          61000              45   

   Loyalty_Years  
0              2  
1              5  
2              4  

Last 3 Records:
    Customer_ID Customer_Name Region  Age  Annual_Income  Spending_Score  \
5          106         Manoj  South   45          90000              55   
6          107          Sita   East   28          64000              70   
7          108          Amit   West   40          58000              60   

   Loyalty_Years  
5              7  
6              3  
7              4  

```
## Input 4
```
# Step 5: Sort customers by Annual Income (descending)
print("\nCustomers Sorted by Annual Income:\n", df.sort_values(by="Annual_Income", ascending=False))

```
## Output 4
```
Customers Sorted by Annual Income:
    Customer_ID Customer_Name Region  Age  Annual_Income  Spending_Score  \
5          106         Manoj  South   45          90000              55   
4          105         Divya  North   35          85000              92   
1          102        Rajesh  South   32          72000              62   
6          107          Sita   East   28          64000              70   
2          103         Priya   East   41          61000              45   
7          108          Amit   West   40          58000              60   
0          101         Anita  North   25          55000              78   
3          104        Vikram   West   29          48000              88   

   Loyalty_Years  
5              7  
4              6  
1              5  
6              3  
2              4  
7              4  
0              2  
3              3  

[ ]


```
## Input 5
```
# Step 6: Filter high-income customers (Income > 70000)
print("\nHigh Income Customers (Income > 70000):\n", df[df["Annual_Income"] > 70000][["Customer_Name", "Annual_Income"]])

```
## Output 5
```
High Income Customers (Income > 70000):
   Customer_Name  Annual_Income
1        Rajesh          72000
4         Divya          85000
5         Manoj          90000
```
## Input 6
```
# Step 7: Group customers by Region and find average Income and Spending Score
print("\nRegion-wise Average Income and Spending Score:")
print(df.groupby("Region")[["Annual_Income", "Spending_Score"]].mean())

```
## Output 6
```
Region-wise Average Income and Spending Score:
        Annual_Income  Spending_Score
Region                               
East          62500.0            57.5
North         70000.0            85.0
South         81000.0            58.5
West          53000.0            74.0

```
## Input 7
```
# Step 8: Count number of customers in each Region
print("\nCustomer Count per Region:")
print(df["Region"].value_counts())

```
## Output 7
```
Customer Count per Region:
Region
North    2
South    2
East     2
West     2
Name: count, dtype: int64

```
## Input 8
```
# Step 9: Identify customer with maximum Spending Score
max_spender = df.loc[df["Spending_Score"].idxmax()]
print("\nTop Spender Details:\n", max_spender)
```
## Output 8
```
Top Spender Details:
 Customer_ID         105
Customer_Name     Divya
Region            North
Age                  35
Annual_Income     85000
Spending_Score       92
Loyalty_Years         6
Name: 4, dtype: object
```

## Input 9
```
#Step 10: Compute overall averages
print("\nAverage Annual Income:", df["Annual_Income"].mean())
print("Average Spending Score:", df["Spending_Score"].mean())

```
## Output 9
```
Average Annual Income: 66625.0
Average Spending Score: 68.75
```

## Result
The program successfully creates a customer dataset using Pandas and performs exploratory analysis, sorting, filtering, regional grouping, and summary statistics.
