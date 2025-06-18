Here's your updated `README.md` incorporating all the details from your Lab 4 implementation:

```markdown
# DataWarehousing-Lab4
# ETL Pipeline Extension Lab

**Student Name:** [Tanveer Omar]

---

## Description

This repository contains a Jupyter Notebook (`lab4.ipynb`) demonstrating an extended ETL (Extract, Transform, Load) pipeline with enhanced functionality. The lab builds upon previous ETL concepts with these key features:

1. **Dynamic Data Generation:** 
   - Automatically generates and appends new transactional data to `custom_data.csv`
   - Simulates realistic e-commerce transactions with timestamps, customer data, and product information

2. **Dual Extraction Modes:**
   - **Full Extraction:** Loading the entire dataset
   - **Incremental Extraction:** Loading only new/updated records since last run using timestamp tracking

3. **Comprehensive Data Transformation:**
   - Robust cleaning, standardization and enrichment processes
   - Complete with error handling and logging throughout the pipeline

---

## Tools Used

* **Python 3:** Core programming language
* **Pandas:** Data manipulation and analysis
* **Jupyter Notebook:** Interactive development environment
* **Datetime:** For timestamp handling and data generation
* **OS:** For file system operations

---

## Key Features

### Data Generation System
- Generates 30+ new records with realistic attributes:
  - Transaction dates starting from June 1, 2025
  - Random but realistic customer names (Amazon, Walmart, etc.)
  - Diverse product categories (Electronics, Home Goods, etc.)
  - Varied payment methods and statuses
  - Automatic record ID management
  - Last updated timestamps for incremental extraction

### Extraction System
```python
def get_last_timestamp(file_path):
    """Smart timestamp retrieval with fallback to minimum datetime"""
    # Implementation details...
```

- Maintains state between runs via `last_extraction.txt`
- Handles first-run scenarios gracefully
- Provides detailed logging of extraction results

### Transformation Pipeline
```python
def apply_transformations(df):
    """Comprehensive data cleaning and enrichment"""
    # Implementation details...
```

**Processing Steps:**
1. **Data Cleaning:**
   - Duplicate removal by record_id
   - Whitespace stripping from all text fields
   - Status field standardization (title case)
   - Null value handling in critical columns

2. **Data Enrichment:**
   - Calculates `total_price` (quantity × amount)
   - Proper datetime conversion for all timestamp fields
   - Numeric type conversion for amount/quantity

3. **Structural Improvements:**
   - Column renaming for consistency
   - Selective column retention
   - Memory-efficient type conversions

---

## How to Use

### Initial Setup
```bash
git clone https://github.com/TanveerD1/DataWarehousing-Labs.git
cd DataWarehousing-Lab3
pip install pandas jupyter
```

### Running the Pipeline
1. Execute all cells in `lab4.ipynb`
2. The system will:
   - Generate new data if needed
   - Perform full extraction and transformation
   - Perform incremental extraction (if new data exists)
   - Update the last extraction timestamp

### Output Files
- `custom_data.csv`: Master dataset (auto-growing)
- `transformed_full.csv`: Cleaned full dataset
- `transformed_incremental.csv`: Cleaned new data only
- `last_extraction.txt`: Timestamp tracking file

---

## Transformation Details

### Applied to Both Full and Incremental Data
1. **Duplicate Handling**  
   `df.drop_duplicates(subset=['record_id'], keep='first')`

2. **Text Normalization**  
   `df[col] = df[col].str.strip()` for all string columns

3. **Type Conversions**  
   - `pd.to_datetime()` for timestamp fields  
   - `pd.to_numeric()` for amount/quantity

4. **Business Logic**  
   `df['total_price'] = df['quantity'] * df['amount']`

5. **Column Standardization**  
   - `record_id` → `transaction_id`  
   - `customer_name` → `customer`  
   - etc.

---

## Error Handling
The pipeline includes comprehensive error handling for:
- File I/O operations
- Data type conversions
- Missing data scenarios
- Extraction boundary cases

All errors are caught and logged with descriptive messages.

---

## Submission Details
This project is submitted as part of the DSA 2040A- LAB 4 US 2025 Take-Home Lab.
```
