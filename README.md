# DataWarehousing-Lab3
# ETL Extract Lab

**Student Name:** [Tanveer Omar]
---

## Description

This repository contains a Jupyter Notebook (`etl_extract.ipynb`) demonstrating the fundamental concepts of data extraction in an ETL (Extract, Transform, Load) pipeline. It specifically implements and showcases two primary extraction methodologies:

1.  **Full Extraction:** Loading the entire dataset at once.
2.  **Incremental Extraction:** Loading only new or updated records since the last successful extraction.

The project utilizes a synthetic sales dataset (`custom_data.csv`) generated for this lab to simulate real-world data scenarios, allowing for practical application of these extraction techniques.

---

## Tools Used

* **Python 3:** The primary programming language.
* **Pandas:** A powerful data manipulation and analysis library for Python.
* **Jupyter Notebook:** An interactive computing environment used for developing and presenting the ETL extraction logic.

---

## How to Reproduce

To run this project and observe the extraction processes:

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/YourUsername/ETL_Extract](https://github.com/YourUsername/ETL_Extract)_<YourFullName>_<StudentID>.git
    cd ETL_Extract_<YourFullName>_<StudentID>
    ```
2.  **Generate Data:**
    Ensure you have the `generate_data.py` script (provided separately or from previous steps). Run it to create the `custom_data.csv` file:
    ```bash
    python generate_data.py
    ```
    *The `custom_data.csv` file is a synthetic dataset generated specifically for this lab. It contains sales records with various attributes, including a `last_updated_timestamp` crucial for incremental extraction.*

3.  **Set up `last_extraction.txt`:**
    Create a file named `last_extraction.txt` in the root directory of the project and add the following content to it. This file simulates the timestamp of a previous extraction.
    ```
    1970-01-01T00:00:00.000000
    ```

4.  **Install Dependencies:**
    Make sure you have `pandas` installed. If not, you can install it using pip:
    ```bash
    pip install pandas jupyter
    ```

5.  **Run the Jupyter Notebook:**
    Start a Jupyter Notebook server from the project's root directory:
    ```bash
    jupyter notebook
    ```
    Then, open `etl_extract.ipynb` in your browser and run all cells sequentially to see the full and incremental extraction in action.

---

## Submission Details

This project is submitted as part of the DSA 2040A- LAB 3 US 2025 Take-Home Lab.
