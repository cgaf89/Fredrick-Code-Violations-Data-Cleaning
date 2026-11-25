# Frederick, MD Code Enforcement Violations — Data Cleaning Project

A cleaned, deduplicated, and standardized dataset of municipal code enforcement violations in Frederick, Maryland (2012–2014), prepared for exploratory data analysis and reporting.

## Project Overview
Raw municipal open-data exports often contain duplicate case entries, inconsistent text casing, and unstandardized date formats that interfere with accurate querying and visualization. This project documents the step-by-step cleaning workflow used to transform a raw export of 6,365 records into an analysis-ready CSV of 5,231 unique enforcement cases.

## Data Cleaning Pipeline
* **Deduplication:** Audited `Violation Case Number` as the primary unique identifier, identifying and removing 1,134 duplicate entries while retaining the 5,231 unique case records.
* **Date & Time Standardization:** Converted mixed-format `Received` timestamps into uniform `YYYY-MM-DD` ISO date strings for accurate chronological sorting and filtering.
* **Text Normalization:** Standardized inconsistent capitalization across categorical fields (e.g., normalizing `patrol` to `Patrol`) to prevent split groupings during aggregation.
* **Structural Cleanup:** Removed temporary helper columns, trimmed trailing blank rows, and sorted all records ascending by `Violation Case Number`.

## Dataset Schema

| Column | Description |
| :--- | :--- |
| `Violation Case Number` | Unique municipal enforcement case identifier (e.g., `CE-14-01760`) |
| `Violation` | Specific code violation code and description |
| `Case Type` | Enforcement division or ordinance category (`CITY CODE`, `PROPERTY MAINTENANCE`, `LAND MANAGEMENT CODE (HPC)`) |
| `Inspector` | Assigned municipal code inspector |
| `Status` | Current case status (`Open`, `Closed`) |
| `Infraction` | Detailed infraction classification |
| `Complaint` | Intake source (`In Person`, `Phone`, `Patrol`, `email`, `Anonymous`) |
| `Received` | Standardized ISO date (`YYYY-MM-DD`) when the complaint was logged |
| `Parcel` | Municipal property parcel identifier |
| `Location` | Street address of the reported violation in Frederick, MD |

## Repository Files
* `frederick_code_violations_clean.csv` — Final deduplicated and standardized dataset (5,231 rows).
* `README.md` — Project documentation and cleaning methodology.
