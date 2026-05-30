# Task 1: Data Cleaning and Preprocessing

## Objective

The objective of this task was to clean and preprocess a raw retail dataset by handling missing values, duplicate records, invalid entries, inconsistent formats, and preparing the data for further analysis.

---

## Dataset Information

- Dataset: Online Retail II
- Source: Online Retail Dataset
- File Format: Excel (.xlsx)
- Sheet Used: Year 2010-2011
- Original Rows: 541,910

---

## Tools Used

- Microsoft Excel
- Python
- Pandas
- Jupyter Notebook / VS Code

---

## Data Cleaning Workflow

### Step 1: Initial Cleaning in Excel

Performed the following operations using Microsoft Excel:

- Removed leading and trailing spaces from:
  - Invoice
  - StockCode
  - Description
  - Country

- Identified missing values using filters

- Removed rows with:
  - Missing Customer ID
  - Missing Description

- Removed cancelled invoices (Invoice numbers starting with "C")

- Removed records with:
  - Quantity ≤ 0
  - Price ≤ 0

- Removed duplicate records

---

### Step 2: Data Processing in Python (Pandas)

Performed additional preprocessing using Python:

- Loaded cleaned Excel dataset using Pandas

- Converted Customer ID from float to integer format

  Example:

  ```
  17850.0 → 17850
  ```

- Standardized InvoiceDate format

  ```
  YYYY-MM-DD HH:MM:SS
  ```

- Created a new feature:

  ```
  TotalAmount = Quantity × Price
  ```

- Rounded TotalAmount values to 2 decimal places

- Verified data types

- Checked for remaining null values

- Exported final cleaned dataset to CSV format

---

## Cleaning Summary

| Operation | Rows Removed |
|------------|-------------|
| Missing Customer ID | 135,080 |
| Missing Description | 1,454 |
| Cancelled Invoices | 9,288 |
| Invalid Quantity | 10,624 |
| Invalid Price | 2,517 |
| Duplicate Records | 5,268 |

---

## Final Dataset

- Rows: 392,693
- Columns: 9
- Null Values: 0
- Duplicate Records: 0

---

## New Feature Added

### TotalAmount

Formula:

```
TotalAmount = Quantity × Price
```

Purpose:

- Calculate transaction value
- Useful for sales and revenue analysis

---

## Output Files

### Input

- online_retail_II.xlsx

### Output

- online_retail_2010_2011_cleaned.csv

---

## Skills Demonstrated

- Data Cleaning
- Data Preprocessing
- Excel Data Handling
- Pandas Data Manipulation
- Missing Value Treatment
- Duplicate Removal
- Data Standardization
- Feature Engineering
- Data Quality Assessment

---

## Repository Structure

```
Task-1-Data-Cleaning-and-Preprocessing/
│
├── online_retail_II.xlsx
├── online_retail_2010_2011_cleaned.csv
├── data_cleaning.py
├── README.md
```

---

## Conclusion

The Online Retail II dataset was successfully cleaned using a combination of Excel and Python. Missing values, duplicate records, cancelled transactions, and invalid entries were removed. Data formats were standardized and a new transaction value feature was created. The final dataset is clean, consistent, and ready for analysis or visualization.# Task-1-Data-Cleaning-and-Preprocessing