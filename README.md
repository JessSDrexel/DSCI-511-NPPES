# NPPES Provider Data Extraction and Classification

## Project Overview
This portion of the project builds on a structured dataset of healthcare providers using the NPPES NPI Registry API and NUCC Taxonomy reference dataset. The objective of this part of the project is to extract provider information such as their NPI identifiers, location, specialty taxonomy codes, and organize it into a dataset that can be used for further healthcare analysis. The dataset is designed so it can later be combined with other healthcare datasets to evaluate whether access to certain provider specialites or preventative care services may have a correlation with specific healthcare outcomes such as unplanned hospital visits.

## Data Aquisition Sources

### NPPES NPI Registry API
The primary data source is the National Provider Identifier (NPI) Registy API maintained by the Centers for Medicare and Medicaid Services (CMS).

API documentation: https://npiregistry.cms.hhs.gov/api-page
API link: https://npiregistry.cms.hhs.gov/api/?version=2.1

The API returns provier information in JSON format which includes:

- NPI number
- provider status
- practice address
- taxonomy codes
- taxonomy descriptions

## NUCC Taxonomy Dataset
The NUCC taxnoomy dataset is used as a supplemental reference file to map provider taxonomy codes returned by the NPPES API to help standardize classifcations, grouping, and specializations.

NUCC link: https://nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40/csv-mainmenu-57
NUCC file used: nucc_taxonomy_251.csv
NUCC version: Version 25.1, 7/1/25 & 1/1/26

The dataset provides taxonomy data which includes:

- Code
- Grouping
- Classification
- Specialization
- Display Name

Taxonomy codes returned from API are matched to this dataset to standardize provider classifications.

## Potential Use of the Dataset
This dataset can be used to analyze the distribution of healthcare providers across geographic areas. It may be useful for examining the relationship between provider availability and healthcare outcomes such as hospital utilization or access to preventative care.

## Challenges and Limitations
API rate limits: The NPPES API limits the number of requests that can be made within a short period of time.
Multiple taxonomy codes: Providers may have multiple taxonomy codes, which can result in multiple rows for a single provider.
Address variability: Provider addresses may not always match exactly with other datasets when linking by geographic information.
Incomplete data: Some providers may have incomplete taxonomy or address data, which can impact classification accuracy.

# Future Development
Possible improvments:

- Expanding queries to include additional zip codes
- Refining provider classification categories
- Linking provider counts with healthcare outcome datasets
- Permorning geographic analysis of provider access

## How to Run the Project

1. Open the notebook Code.ipyng in Jupyter Notebook or Google Colab.
2. Ensure the file 'nucc_taxonomy_251.csv' is available in the project directory.
3. Install required libraries if needed (ex: pip install pandas requests)
4. Run the notebook cells in order to retrieve and process the provider data.
