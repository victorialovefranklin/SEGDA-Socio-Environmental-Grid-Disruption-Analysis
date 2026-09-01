# Required Input Files

The SEGDA script currently expects the following inputs:

| Role | Expected filename |
|---|---|
| CalEnviroScreen | `CalEnviroScreen_4.0.csv` |
| Tract SVI | `SVI_CA_TRACT.csv` |
| County SVI | `California_SVI_2022.csv` |
| 2019 Census tract geometry | `tl_2019_06_tract.shp` |
| 2019 Census county geometry | `tl_2019_us_county.shp` |
| Modeled County Customers | `MCC.csv` |
| FEMA NRI | `NRI_Table_Counties_California.csv` |
| Reconstructed EAGLE-I episodes | `eaglei_transformed.csv` |
| EIA-861 historical county reliability summary | `SEGDA_EIA861_CA_COUNTY_RELIABILITY_6YR_SUMMARY.csv` |

## Shapefile note

A `.shp` file is not sufficient by itself. Keep its associated `.shx`, `.dbf`, `.prj`, and `.cpg` files together in the same data directory.


The script records SHA-256 hashes for resolved inputs as part of its provenance workflow.
