# elevate_da_tasks
# 📺 Netflix Movies and TV Shows Dataset - Preprocessing Summary

## 🧹 Data Cleaning Overview

The dataset was cleaned and prepared for analysis using the following steps:

- **Missing Values:**
  - 'director' (2,389), 'cast' (718), and 'country' (507) were imputed with `'Unknown'`.
  - Rows with missing 'date_added' (10) and 'rating' (7) were removed.

- **Duplicate Records:**
  - No duplicate rows were found.

- **Text Standardization:**
  - Converted text in key columns to **lowercase** and removed **leading/trailing spaces**.

- **Date Format Conversion:**
  - 'date_added' was successfully converted to `datetime64[ns]` using `pd.to_datetime()`.

- **Column Header Formatting:**
  - All column headers were standardized: lowercase with spaces replaced by underscores.

- **Data Type Verification:**
  - Data types were confirmed to be appropriate. No further type conversion was needed.


