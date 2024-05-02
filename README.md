# Reporting
**Project Title:** IDP Report Generation

**Overview**

This script automates the generation of an IDP (Intelligent Document Processing) report. Its key functions include:

* **Data Preparation**:
  * Retrieves the current day's dataset.
  * Preprocesses the data, including sorting, filling missing values, and flagging relevant records.
* **Analysis and Calculations:**
  * Calculates match accuracy between RA labels and IDP-predicted labels.
  * Flags documents and individual pages with mismatches.
  * Identifies documents within a prioritized "Top 60" list.
* **Reporting:**
  * Updates a Google Sheet ("Pages") with the processed data.
  * Appends results to a Google Sheet ("Daily Results") for historical tracking.
  * Calculates metrics relevant for an IDP performance dashboard.
  * "Today's Results" sheet: Aggregates daily metrics, including date.

**Dependencies**

**Python 3**
* **pandas** (Data manipulation library)
* **gspread** (Google Sheets API interaction)
* **gspread_dataframe** (Simplifies updating Google Sheets with DataFrames)
**Installation**

**Google Drive Setup**

1. Create a Google Sheet titled "IDP Report".
2. Within the sheet create two worksheets: "Pages" and "Daily Results".
3. Ensure the script has the necessary permissions to edit these sheets (refer to gspread documentation for authentication).

**Usage**

1. **Authentication:** Follow the instructions from the gspread library to authenticate your Google Drive account.
2. **Datasets:** Update the file paths for 'Pages.csv', and 'top60.csv' to match your data sources.
3. **Run the script:** Execute the "IDP Report.ipynb" notebook.

**Code Explanation**

* **"Get Today's Dataset"**: Imports and pre-processes today's IDP data.
* **"Update all_Pages_dataset_133"**: Updates the master "Pages" sheet in your Google Sheets document with the processed information.
* **"Add Pivot table to daily results"**: Appends today's result to the "Today's Results" sheet and updates the historical "Daily Results" sheet.
* **"Dashboard Update"**: Prepares comparison metrics for dashboard updates.

**Important Notes**

The script assumes specific Google Sheet structures. Modify as needed if your sheets differ.
Adjust the file paths in the script to match your datasets correctly.
