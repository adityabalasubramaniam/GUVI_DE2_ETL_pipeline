================================================================================
      DE_A Comprehensive ETL Workflow with Python for Data Engineers
================================================================================

Author           : Aditya Balasubramaniam
Project Name     : ETL Data Pipeline - Multi-Format Extraction & Transformation
Last Updated     : August 2025

================================================================================
1. INTRODUCTION
--------------------------------------------------------------------------------
This project demonstrates a full ETL (Extract, Transform, Load) data pipeline 
built using Python. It automates the ingestion of multiple data formats 
(CSV, JSON, XML), performs standardized transformations including unit 
conversions, handles data quality issues like duplicates and missing values, 
and stores the cleaned data in a CSV file for downstream use.

The ETL process includes logging for auditability, traceability, and debugging 
purposes.

================================================================================
2. OBJECTIVES
--------------------------------------------------------------------------------
- Extract structured and semi-structured data from various file formats.
- Transform the data into consistent units and structure.
- Clean the dataset by handling missing values and removing duplicates.
- Load the transformed data into a unified CSV output.
- Maintain detailed logs of the entire ETL process.

================================================================================
3. TECHNOLOGIES USED
--------------------------------------------------------------------------------
- Language     : Python 3.8+
- Libraries    : pandas, requests, glob, xml.etree.ElementTree, zipfile, datetime
- Tools        : Jupyter Notebook, Git, GitHub
- Format Types : CSV, JSON, XML

================================================================================
4. DATASET
--------------------------------------------------------------------------------
Dataset Source:
IBM Developer Skills Network - ETL Practice Dataset

Download Link:
https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/
IBMDeveloperSkillsNetwork-PY0221EN-SkillsNetwork/labs/module%206/
Lab%20-%20Extract%20Transform%20Load/data/source.zip

Download via CLI:
```bash
wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0221EN-SkillsNetwork/labs/module%206/Lab%20-%20Extract%20Transform%20Load/data/source.zip
unzip source.zip -d ./unzipped_folder
```

================================================================================
5. ETL PIPELINE STRUCTURE
--------------------------------------------------------------------------------
The project follows a modular ETL pipeline with clear separation of concerns.

PHASE 1: EXTRACTION
-------------------
- Identify and load CSV, JSON, and XML files from the unzipped directory.
- Normalize each format into pandas DataFrames.
- Combine all data sources into a single DataFrame.

PHASE 2: TRANSFORMATION
-----------------------
- Fill missing values with default (zero).
- Remove duplicate rows based on all columns.
- Convert height from inches to meters: `1 inch = 0.0254 meters`
- Convert weight from pounds to kilograms: `1 pound = 0.453592 kilograms`

PHASE 3: LOAD
-------------
- Save the final cleaned and transformed DataFrame into `transformed_data.csv`.

PHASE 4: LOGGING
----------------
- Each step is timestamped and written to `logs_file.txt`.
- This allows traceability of the pipeline execution.

================================================================================
6. FILE STRUCTURE
--------------------------------------------------------------------------------
/etl-multiformat-pipeline/
│
├── DE_proj2.ipynb          # Jupyter Notebook with complete ETL code
├── logs_file.txt              # Log file capturing each ETL step
├── transformed_data.csv       # Output of the ETL process
├── README.txt                 # This documentation file
└── unzipped_folder/           # Contains extracted CSV, JSON, and XML files

================================================================================
7. HOW TO RUN
--------------------------------------------------------------------------------
1. Open the `DE_proj2.ipynb` notebook.
2. Run all cells to execute the full ETL process.
3. Output files (`transformed_data.csv` and `logs_file.txt`) will be generated.

================================================================================
8. FUTURE ENHANCEMENTS
--------------------------------------------------------------------------------
- Add error handling and retry mechanisms.
- Parameterize file paths and formats using config files or CLI args.
- Integrate Apache Airflow or Prefect for workflow orchestration.
- Store logs in a central logging system (e.g., ELK stack).
- Store final outputs in a database like PostgreSQL or Snowflake.

================================================================================
9. LICENSE
--------------------------------------------------------------------------------
This project is licensed under the MIT License - see the LICENSE file for details.

================================================================================
10. CONTACT
--------------------------------------------------------------------------------
For queries, reach out via GitHub Issues or contact:
Aditya Balasubramaniam
[https://github.com/adityabalasubramaniam]
================================================================================
