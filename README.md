Let's get your `README.md` updated! I'll incorporate the new Lab 4 details about data transformation, adjust the notebook name to `lab4.ipynb`, and clarify the data setup since `custom_data.csv` is now assumed to be in the repo.

Here's the updated `README.md` content:

---

# DataWarehousing-Lab3
# ETL Extract & Transform Lab

**Student Name:** [Tanveer Omar]

---

## Description

This repository contains a Jupyter Notebook (`lab4.ipynb`) demonstrating the fundamental concepts of an ETL (Extract, Transform, Load) pipeline, with a strong focus on **data extraction and transformation**. It specifically implements and showcases:

1.  **Full Extraction:** Loading the entire dataset at once.
2.  **Incremental Extraction:** Loading only new or updated records since the last successful extraction.
3.  **Data Transformation:** Applying various techniques to clean, enrich, and structure the extracted data for analysis.

The project utilizes a synthetic sales dataset (`custom_data.csv`) to simulate real-world data scenarios, allowing for practical application of these ETL techniques.

---

## Tools Used

* **Python 3:** The primary programming language.
* **Pandas:** A powerful data manipulation and analysis library for Python.
* **Jupyter Notebook:** An interactive computing environment used for developing and presenting the ETL logic.

---

## Transformation Techniques Implemented

The `lab4.ipynb` notebook applies a series of transformations to both the full and incremental datasets to prepare them for analysis:

* **Cleaning:**
    * **Duplicate Removal:** Identifies and removes duplicate records based on `record_id`.
    * **Whitespace Stripping:** Removes leading and trailing whitespace from string-based columns (`customer_name`, `product_category`, `payment_method`, `status`).
    * **Standardized Casing:** Ensures consistency in the `status` column (e.g., "Completed", "Pending", "Cancelled").
    * **Missing Value Handling:** Drops rows where critical columns (`amount`, `quantity`, `transaction_date`, `transaction_timestamp`) have invalid or missing values after type conversion.

* **Enrichment:**
    * **Calculated Column (`total_price`):** Adds a new column by multiplying `quantity` and `amount`, providing immediate business value.

* **Structural:**
    * **Data Type Conversion:** Converts relevant columns (`transaction_date`, `transaction_timestamp`, `last_updated_timestamp`, `amount`, `quantity`) to their appropriate data types (datetime, numeric).
    * **Column Selection & Renaming:** Selects a focused set of relevant columns and renames them for better clarity and consistency (e.g., `record_id` to `transaction_id`, `customer_name` to `customer`, `product_category` to `category`, `payment_method` to `payment_type`).

---

## How to Reproduce

To run this project and observe the ETL processes:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/TanveerD1/DataWarehousing-Lab3.git
    cd DataWarehousing-Lab3
    ```
2.  **Ensure Data File Exists:**
    Make sure the `custom_data.csv` file is present in the root directory of the cloned repository. This file is the source for all extractions.
    *(Note: This lab assumes `custom_data.csv` is already available and does not include data generation within the notebook.)*

3.  **Set up `last_extraction.txt` (Optional for First Run):**
    For incremental extraction to work correctly, a `last_extraction.txt` file is used to store the last successful extraction timestamp.
    * If this is your **first run**, the script will create it.
    * If you want to simulate a specific past extraction point, you can manually create `last_extraction.txt` with an ISO-formatted timestamp (e.g., `1970-01-01T00:00:00.000000`).

4.  **Install Dependencies:**
    Make sure you have `pandas` and `jupyter` installed. If not, you can install them using pip:
    ```bash
    pip install pandas jupyter
    ```

5.  **Run the Jupyter Notebook:**
    Start a Jupyter Notebook server from the project's root directory:
    ```bash
    jupyter notebook
    ```
    Then, open **`lab4.ipynb`** in your browser and run all cells sequentially to see the full extraction, incremental extraction, and data transformation in action.

---

## Submission Details

This project is submitted as part of the DSA 2040A- LAB 4 US 2025 Take-Home Lab.

---