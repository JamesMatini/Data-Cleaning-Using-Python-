# 🧹 Data Cleaning Using Python

A comprehensive and practical data cleaning workflow applied to a marketing campaign dataset using **Python**, **Pandas**, and **NumPy**. This project covers real-world data quality issues and demonstrates a step-by-step transformation process to produce an analysis-ready dataset.

---

## 📊 Project Overview

The dataset contains marketing campaign performance metrics with inconsistencies, invalid entries, mixed formats, and logical errors. This notebook walks through identifying, fixing, and validating these issues to ensure clean, consistent, reliable data for downstream analytics.

---

## 📁 Dataset Information

- **File:** `marketing_campaign_data_messy.csv`  
- **Original Size:** 2020 rows × 12 columns  
- **Cleaned Size:** 2020 rows × 11 columns  
- **Source Path:** `C:/Users/Ajira eMobilis/marketing_campaign_data_messy.csv`

---

## 🎯 Data Quality Issues Identified

### 1. **Inconsistent Column Headers**
- Extra whitespace  
- Mixed casing  
- Duplicate column names  

### 2. **Data Type Issues**
- Currency values stored as strings  
- Boolean values represented inconsistently  
- Dates stored as strings  

### 3. **Categorical Issues**
- Typos in channel names  
- Multiple boolean representations (Yes/No, Y/N, 1/0, True/False)

### 4. **Logical Integrity Problems**
- Clicks > impressions  
- End dates earlier than start dates  
- Extreme spend outliers  

### 5. **Feature Engineering Opportunities**
- Extracting season information from campaign names  

---

## 🔧 Cleaning Steps Performed

### 1. **Column Header Standardization**
- Trimmed whitespace  
- Converted to lowercase  
- Replaced spaces with underscores  
- Removed duplicate columns  

### 2. **Currency Cleaning**
- Stripped “$” and other non-numeric characters  
- Converted `spend` to a numeric dtype  

### 3. **Boolean Standardization**
Standardized all representations to **True/False**.  
Examples: Yes/Y/1/True → **True**, No/N/0/False → **False**

### 4. **Date Parsing**
- Converted string dates to `datetime`  
- Used `dayfirst=True`  
- Applied `errors='coerce'` for invalid dates  

### 5. **Categorical Cleaning**
- Corrected typos in channel names  
- Standardized categories (Facebook, Instagram, Google Ads, TikTok, Email)

### 6. **Logical Validation**
- Flagged cases where clicks > impressions  
- Corrected invalid date relationships  
- Winsorized extreme spend values (capped at **3 × IQR**)  

### 7. **Feature Engineering**
- Extracted season information using regex  
- Created new column: `season`

---

## 📈 Key Metrics After Cleaning

- **Duplicate Columns Removed:** 1 (`Clicks`)  
- **Data Type Fixes:**  
  - `spend`: object → float64  
  - `active`: object → bool  
  - `start_date`, `end_date`: object → datetime64  
- **Boolean Standardization:** Reduced 7 patterns → 2 (True/False)  
- **Channel Clean-up:** Normalized 6 channel values  

---

## 🛠️ Technologies Used

- **Python 3.13.5**  
- **Pandas** — data manipulation  
- **NumPy** — numerical processing  
- **Jupyter Notebook** — execution environment  

---

## 📋 Notebook Structure

1. Load & inspect dataset  
2. Clean column headers  
3. Fix data types  
4. Remove duplicate columns  
5. Standardize categorical and boolean data  
6. Parse and validate dates  
7. Perform logical integrity checks  
8. Handle outliers  
9. Extract new features  

---

## 🎯 Key Functions & Methods Used

- `pd.read_csv()`  
- `df.columns.str.*`  
- `pd.to_numeric()`  
- `df.replace()`  
- `pd.to_datetime()`  
- `.str.extract()`  
- `.quantile()`  
- Boolean indexing  

---

## 📊 Expected Outcomes

After cleaning, the dataset becomes:

- **Consistent** — uniform formatting  
- **Accurate** — valid relationships  
- **Complete** — invalid entries handled cleanly  
- **Analysis-ready** — proper dtypes + engineered features  
- **Enhanced** — season extracted for deeper insight  

---

## 🚀 Usage Instructions

1. Install Python, Pandas, and NumPy  
2. Update the file path in Cell 1  
3. Run the notebook top-to-bottom  
4. Use the cleaned DataFrame (`df`) for analysis or modeling  

---

## 📝 Notes

- Cleaning steps are non-destructive where possible  
- Each major fix outputs a `"FIX APPLIED"` log  
- Intermediate previews help verify changes  
- Overall structure is preserved while data quality is enhanced  

---

## 🔍 Future Improvements

Potential upgrades include:

- Automated anomaly detection  
- Integration with data validation tools (Great Expectations)  
- Reusable cleaning pipeline (class-based)  
- Unit tests for each cleaning step  
- Before/after visualizations  

---

### 📘 This project provides a real-world demonstration of the complexities and methods of professional data cleaning using Python.

