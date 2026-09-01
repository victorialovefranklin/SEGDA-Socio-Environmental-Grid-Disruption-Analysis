# SEGDA Methodology

The public script identifies itself as SEGDA and implements the following locked analytical design:

1. **Strict tract EJBI:** requires CDC/ATSDR SVI `RPL_THEMES`, CalEnviroScreen overall percentile, and CalEnviroScreen Pollution Burden percentile. Negative SVI codes are treated as missing.
2. **County EJBI:** population-weighted mean of valid tract EJBI.
3. **Study-defined High-EJBI:** tract EJBI >= 0.75; county EJBI >= 0.60. These are not official California SB 535 DAC designations.
4. **Primary outage burden:** reconstructed EAGLE-I episodes are deduplicated before OE-417 join expansion; estimated customer-outage-hours are normalized by ORNL Modeled County Customers and transformed using robust IQR normalization.
5. **Sensitivity analyses:** population-normalized outage burden, a branch excluding apparent 34-hour ceiling episodes, and EIA-861 historical reliability sensitivity.
6. **Climate Stress:** unweighted mean of min-max normalized FEMA NRI risk scores for drought, heat wave, wildfire, riverine flood, earthquake, strong wind, and tornado.
7. **Spatial analysis:** Queen-contiguity weights with geometry QA, Global Moran's I, and Local Moran permutation diagnostics.
8. **GRIP:** intentionally excluded from locked SEGDA quantitative results pending project-level verification.

The code also produces tables, sensitivity correlations, QA/provenance outputs, publication figures, and validation reports.
