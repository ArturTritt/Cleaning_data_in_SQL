<img width="701" height="476" alt="image" src="https://github.com/user-attachments/assets/38b52910-40ad-4148-a085-5e40b9803bec" />


**# Cleaning_data_in_MySQL**


Project Summary: Customer Order Data Cleaning and Standardisation
This project focused on using SQL to clean and standardise a raw customer order dataset. The goal was to transform messy, inconsistent data into a structured and reliable format suitable for further analysis and reporting.
This analysis reveals the types of data that I have created myself.

**Key Insights & Findings:**
The analysis uncovered several data inconsistencies that required cleaning, including:
  1. Missing and inconsistent data: The customer_name and email columns contained missing values and inconsistent formatting.
  2. Typographical errors: The quantity column contained non-numeric text ('one', 'two').
  3. Formatting issues: The order_date column had a mix of different date formats (YYYY-MM-DD, MM/DD/YYYY).
  4. Non-standardised categories: product_name, order_status, and country contained inconsistent values and spelling errors ('Pakistan', 'UK', 'CANADA').

**SQL Techniques & Queries Used:**
  The data was cleaned and standardised using a combination of DDL and DML operations. Key SQL techniques included:
  
Data Type Conversion (ALTER TABLE & CAST):
  - The order_id column was permanently converted to an INT data type.
  - The price and quantity columns were converted from text to numeric types (DECIMAL and FLOAT).

String Manipulation (LOWER, UPPER, REPLACE):
  - The customer_name column was standardised to a single case using UPPER().
  - The price column was cleaned by removing currency symbols using REPLACE().

Conditional Logic (CASE WHEN):
  - The CASE WHEN statement was extensively used to standardise values in the order_status, product_name, and country columns by grouping similar entries (e.g., 'UK' and 'United Kingdom') into a single, clean value.
  - Window Functions & CTEs (ROW_NUMBER, WITH): A ROW_NUMBER() window function was used within a CTE (deduplicated_data) to identify and remove duplicate rows based on unique combinations of email and product_name.
This ensured each unique order was represented only once. 

Subqueries (SELECT * FROM (SELECT...)):
  - The entire cleaning process was structured using a series of CTEs to build a logical and easy-to-read pipeline, moving from a cleaned_data set to a final_table that was deduplicated and ready for analysis.

**Final Result:**
The final result is a clean, well-structured dataset where each order is unique, all values are standardised, and data types are correctly formatted. This processed data is now ready for direct use in a Business Intelligence tool like Power BI to create accurate reports and dashboards.

<img width="1444" height="208" alt="image" src="https://github.com/user-attachments/assets/1506cdaa-77cc-4d04-83b2-fd1445547fdd" />

