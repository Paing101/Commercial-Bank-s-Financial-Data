# Commercial-Bank-s-Financial-Data
Commercial Bank's Financial Data Cleaning (This project is created for the educational purpose)

Project Overview

This project automates the Extraction, Transformation, and Loading (ETL) process for multiple financial datasets. The script processes several Excel workbooks with inconsistent header structures, unpivots time-series data into a tidy format, and consolidates them into a single, analysis-ready Master Dataset.

FeaturesDynamic Header Detection: Automatically scans Excel files to find the correct data starting point, bypassing varying amounts of metadata rows.Data Reshaping (Melting): Transforms wide-format financial reports (months as columns) into long-format datasets (rows representing individual observations).Automated Data Cleaning: * Strips whitespace from labels.Converts month names to chronological integers.Ensures numeric types for financial amounts.Source Tracking: Appends a "File Name" column to every row to maintain data lineage.Global Serial Numbering: Generates a continuous No. sequence across the entire consolidated dataset.

How It WorksFile Discovery: The script identifies all .xlsx files in a specified directory while ignoring temporary/system files.Transformation Loop:Identify the header row containing "Month" or "No." data.Unpivot (Melt) the month columns into Month_Year rows.Split strings (e.g., "Jan 2020") into separate Month and Year integer columns.

Consolidation: Uses pandas.concat to stack all processed dataframes.Final Formatting: Sorts data chronologically, resets the serial index, and shifts metadata columns to the end.

Tech StackPython 3.xPandas: For data manipulation and reshaping.Openpyxl/XlsxWriter: For Excel file handling.Tqdm: To provide a visual progress bar during the batch processing loop.
