# Task 1: Data Cleaning and Preprocessing
# 🛒 Online Retail — Cleaned Dataset

A cleaned and preprocessed version of the UCI Online Retail Dataset,
ready for data analysis, machine learning, and business intelligence projects.

---

## 📁 Files

| File | Description |
|------|-------------|
| `online_retail_cleaned.csv` | Main cleaned dataset (~20MB, 282K rows) |
| `country_legend.csv` | Country code to country name mapping |
| `online_retail_cleaning.py` | Python cleaning script |

---

## 📊 Dataset Overview

- **Source:** UCI Machine Learning Repository
- **Original Rows:** 541,910
- **Cleaned Rows:** 282,457
- **Columns:** 9

### Columns

| Column | Type | Description |
|--------|------|-------------|
| `Invoice` | string | Unique invoice number |
| `StockCode` | string | Product/item code |
| `Description` | string | Product name |
| `Quantity` | integer | Number of units purchased |
| `InvoiceDate` | date | Date of transaction (YYYY-MM-DD) |
| `Price` | float | Unit price in GBP (£) |
| `Customer ID` | string | Unique customer identifier |
| `Country` | string | Encoded country code (see country_legend.csv) |
| `TotalAmount` | float | Quantity × Price |

---

## 🧹 Cleaning Steps

1. Removed 5,268 duplicate rows
2. Dropped 135,037 rows with missing Customer ID
3. Removed 8,872 cancellation invoices (Invoice starting with 'C')
4. Removed rows with negative or zero Quantity / Price
5. Removed extreme Quantity outliers (above 99.9th percentile)
6. Standardized text formatting (trimmed whitespace, title case)
7. Encoded country names as short codes to reduce file size
8. Added TotalAmount derived column (Quantity × Price)
9. Sampled to keep final file under 20MB

---

## 🐍 Load in Python

```python
import pandas as pd

# Load dataset
df = pd.read_csv("online_retail_cleaned.csv")

# Decode country codes
legend = pd.read_csv("country_legend.csv").set_index("Code")["Country"]
df["Country"] = df["Country"].map(legend)

# Convert date
df["InvoiceDate"] = pd.to_datetime(df["InvoiceDate"])

print(df.shape)
print(df.head())
```

---

## 📊 Load in Excel

1. Open **Microsoft Excel**
2. Go to **Data** tab → **Get Data** → **From File** → **From Text/CSV**
3. Select `online_retail_cleaned.csv` → Click **Import**
4. In the preview window click **Load**
5. For country names, open `country_legend.csv` separately and use
   **VLOOKUP** to decode the Country column:
   ```
   =VLOOKUP(A2, country_legend.csv!$A:$B, 2, 0)
   ```

> **Tip:** For large file performance in Excel, go to
> **Data → From Table/Range** and use **Power Query** to filter
> rows before loading.

---

## 💡 Use Cases

- Customer Segmentation (RFM Analysis)
- Sales Trend Analysis
- Product Recommendation Systems
- Time Series Forecasting
- Market Basket Analysis

---

## 📜 License

Original data from
KAGGLE
For research and educational use only.


