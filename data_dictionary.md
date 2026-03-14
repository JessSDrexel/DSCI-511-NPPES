# Data Dictionary – Provider Preventative Dataset

This dataset contains healthcare provider information retrieved from the NPPES NPI Registry API and enriched with taxonomy classification data from the NUCC Taxonomy dataset.

## Provider Preventative Dataset

| Variable Name | Description | Source | Example |
|---|---|---|---|
| NPI | National Provider Identifier assigned to each healthcare provider | NPPES NPI Registry API | 1790565554 |
| Code | Provider taxonomy code identifying the provider's specialty | NPPES NPI Registry API | 207Q00000X |
| API_Category | High-level category parsed from the taxonomy description returned by the API | NPPES NPI Registry API | Allopathic & Osteopathic Physicians |
| API_Specialty | Specialty parsed from the API taxonomy description | NPPES NPI Registry API | Family Medicine |
| Address_1 | First line of the provider practice address | NPPES NPI Registry API | 3400 SPRUCE ST |
| Address_2 | Second line of the provider practice address if available | NPPES NPI Registry API | STE 500 |
| City | City where the provider practice is located | NPPES NPI Registry API | PHILADELPHIA |
| State | State where the provider practice is located | NPPES NPI Registry API | PA |
| ZIP | ZIP code of the provider practice location | NPPES NPI Registry API | 19104 |
| Grouping | High-level provider grouping associated with the taxonomy code | NUCC Taxonomy Dataset | Allopathic & Osteopathic Physicians |
| Classification | Standard provider classification associated with the taxonomy code | NUCC Taxonomy Dataset | Family Medicine |
| Specialization | More specific provider specialization if available | NUCC Taxonomy Dataset | Sports Medicine |
| Display Name | Standard taxonomy display name for the provider type | NUCC Taxonomy Dataset | Family Medicine Physician |
| Preventative_Category | Custom category created in this project to group providers based on preventative care relevance | Derived from taxonomy classification | Primary Preventative Care |

## Notes

- **NPPES NPI Registry API** is the primary data source for provider records.
- **NUCC Taxonomy dataset** is used as a supplemental reference file to map taxonomy codes to standardized provider classifications.
- Preventative_Category is a field created during the data processing stage to group providers by preventative healthcare relevance.
- Providers may appear multiple times if they have multiple taxonomy codes.
