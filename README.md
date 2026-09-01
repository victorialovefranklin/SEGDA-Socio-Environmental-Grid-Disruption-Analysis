 # SEGDA: Socio-Environmental Grid Disruption Analysis

### A Multi-Scale Spatial Assessment of Energy Justice and Climate Resilience Across California Census Tracts and Counties, 2018–2023

**Victoria Love Franklin**  
Ph.D. Data Science Research Scholar  
Published Research Author  

**Conference:** EAI SmartGIFT 2026  
**Publication:** Springer LNICST Proceedings — Pending  
**Repository Version:** SEGDA    
**Study Period:** 2018–2023  
**Study Area:** California, USA  

---

## Overview

Socio-Environmental Grid Disruption Analysis (SEGDA) is a reproducible, multiscale geospatial framework developed to examine the relationships among environmental justice, electricity-outage exposure, climate stress, and social vulnerability.

The framework integrates census-tract and county-level information to evaluate how geographic aggregation can influence the identification and interpretation of vulnerable communities and grid-disruption burden.

The study focuses on California from 2018 through 2023 and combines environmental, demographic, climate-hazard, electricity-outage, and spatial data within a reproducible Python-based analytical workflow.

This repository serves as the **official research code and reproducibility companion repository** for the SEGDA study accepted to EAI SmartGIFT 2026.

---

## Publication

### Accepted Paper

**Franklin, Victoria Love.**  
*Socio-Environmental Grid Disruption Analysis: A Multi-Scale Spatial Assessment of Energy Justice and Climate Resilience Across California Census Tracts and Counties, 2018–2023.*

**Conference:** 10th EAI International Conference on Smart Grid and Innovative Frontiers in Telecommunications (EAI SmartGIFT 2026)

**Proceedings:** Springer, Lecture Notes of the Institute for Computer Sciences, Social Informatics and Telecommunications Engineering (LNICST)

**Publication Status:** Accepted for EAI SmartGIFT 2026; Springer proceedings publication pending.

**Springer DOI:** Pending publication  
**Springer Publication URL:** Pending publication  
**Volume:** Pending publication  
**Page Numbers:** Pending publication  

> The official Springer citation, DOI, volume, page numbers, and publication URL will be added to this repository when the final proceedings metadata are assigned.

The publisher-formatted Springer manuscript is not distributed through this repository. Upon publication, readers will be directed to the official Springer/DOI record.

---

## Research Objectives

SEGDA was developed to:

1. Construct a multicomponent Environmental Justice Burden Index (EJBI).
2. Evaluate environmental-justice burden at census-tract and county scales.
3. Reconstruct and normalize electricity-outage exposure.
4. Evaluate climate stress using selected FEMA National Risk Index hazards.
5. Examine relationships among environmental justice, outage burden, climate stress, and social vulnerability.
6. Quantify the effects of geographic aggregation on localized environmental-justice burden.
7. Evaluate spatial clustering using spatial-autocorrelation analysis.
8. Provide a reproducible framework for multiscale grid-resilience and environmental-justice research.

---

## Analytical Framework

SEGDA integrates four primary analytical dimensions:

### Environmental Justice Burden

The strict tract-level Environmental Justice Burden Index (EJBI) integrates:

- CDC/ATSDR Social Vulnerability Index (SVI)
- CalEnviroScreen overall percentile
- CalEnviroScreen Pollution Burden percentile

The primary analysis requires all three components.

Study-defined High-EJBI thresholds are used for analytical comparison and should not be interpreted as official California SB 535 disadvantaged-community designations.

### Electricity-Outage Burden

Primary outage burden is derived from reconstructed and deduplicated EAGLE-I outage episodes.

Customer-outage-hours are normalized using Modeled County Customers (MCC), with robust normalization incorporated into the analytical pipeline.

EIA-861 reliability measures are used as a sensitivity analysis rather than as a substitute for the primary reconstructed outage-burden measure.

### Climate Stress

Climate stress is constructed using selected hazard indicators from the FEMA National Risk Index.

The climate component provides an additional dimension for evaluating how physical hazard exposure relates to environmental justice and electricity-disruption patterns.

### Spatial and Multiscale Analysis

SEGDA evaluates results at both census-tract and county scales.

The framework specifically examines the **modifiable areal unit problem (MAUP)** and the extent to which county-level aggregation can suppress tract-level variation and conceal localized high-burden communities.

Spatial autocorrelation is evaluated using Moran's I.

---

## Key Findings

The audited SEGDA analysis produced the following principal results:

| Metric | Result |
|---|---:|
| California census-tract geometries | 8,057 |
| Tracts with strict EJBI | 7,931 |
| High-EJBI tracts | 1,690 |
| California counties | 58 |
| High-EJBI counties | 11 |
| Tract-level EJBI variance suppressed by county aggregation | 67.82% |
| High-EJBI tracts masked within counties below county threshold | 431 |
| EJBI vs. Primary Outage Burden Index | r = -0.442 |
| Climate Stress vs. Primary Outage Burden Index | r = -0.565 |
| SVI vs. EJBI | r = 0.829 |
| EJBI Moran's I | 0.202 |
| Primary OBI Moran's I | 0.401 |

A central finding is that **county-level aggregation suppressed 67.82% of tract-level EJBI variance and masked 431 High-EJBI census tracts located within counties that did not meet the study-defined county High-EJBI threshold.**

These results demonstrate the importance of geographic scale when evaluating environmental justice and infrastructure resilience.

Negative associations involving realized outage burden should not be interpreted as evidence that disadvantaged or climate-stressed communities are necessarily better protected. Environmental-justice burden, climate exposure, social vulnerability, and realized outage burden represent related but non-equivalent dimensions and may also be influenced by geographic scale, utility characteristics, infrastructure conditions, and reporting structures.

---

## Data Sources

SEGDA integrates information from multiple authoritative public data sources, including:

- CDC/ATSDR Social Vulnerability Index (SVI)
- California CalEnviroScreen
- DOE EAGLE-I electricity-outage information
- U.S. Energy Information Administration (EIA)
- FEMA National Risk Index (NRI)
- U.S. Census geographic and demographic information

Raw third-party datasets are **not redistributed through this repository**.

Users seeking to reproduce the study should obtain the applicable source datasets directly from their authoritative providers and review:

[`docs/data_sources.md`](docs/data_sources.md)

for additional information.

---

## Repository Structure

```text
SEGDA-Socio-Environmental-Grid-Disruption-Analysis/
│
├── docs/
│   ├── data_sources.md
│   ├── methodology.md
│   └── reproducibility.md
│
├── figures/
│   └── Publication and research figures
│
├── results/
│   └── Selected derived analytical outputs
│
├── src/
│   └── segda.py
│
├── .gitignore
├── CITATION.cff
├── LICENSE
├── README.md
└── requirements.txt
```

---

## Source Code

The primary analytical pipeline is located at:

```text
src/segda.py
```

The repository currently corresponds to:

**SEGDA**

The pipeline includes data validation, environmental justice index construction, outage burden reconstruction, climate stress analysis, multiscale aggregation, statistical analysis, spatial analysis, and publication-quality figure generation.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/victorialovefranklin/SEGDA-Socio-Environmental-Grid-Disruption-Analysis.git
```

Enter the repository:

```bash
cd SEGDA-Socio-Environmental-Grid-Disruption-Analysis
```

Create a Python virtual environment:

```bash
python -m venv .venv
```

Activate the environment and install the required packages:

```bash
pip install -r requirements.txt
```

Primary Python dependencies include:

- GeoPandas
- Matplotlib
- NumPy
- pandas
- SciPy

---

## Running SEGDA

SEGDA supports environment-based configuration for the input-data and output directories.

Set the required paths before running the pipeline.

Example:

```bash
export SEGDA_DATA_DIR="/path/to/segda/data"
export SEGDA_OUTPUT_DIR="/path/to/segda/output"
```

Then run:

```bash
python src/segda.py
```

Windows PowerShell users may configure the variables using:

```powershell
$env:SEGDA_DATA_DIR="C:\path\to\segda\data"
$env:SEGDA_OUTPUT_DIR="C:\path\to\segda\output"
python src/segda.py
```

See:

[`docs/reproducibility.md`](docs/reproducibility.md)

for additional reproducibility instructions.

---

## Figures

Publication and research figures generated from the SEGDA analytical pipeline are maintained in:

```text
figures/
```

The analytical workflow supports publication-quality figure generation, including high-resolution PNG, SVG, and PDF outputs.

Only appropriate author-generated research figures are distributed through this repository. Publisher-formatted Springer materials are not included.

---

## Results

Selected derived research outputs may be provided in:

```text
results/
```

This directory is intended for reproducibility-supporting outputs and selected non-restricted derived results.

Raw third-party datasets are not redistributed.

---

## Reproducibility

SEGDA was designed as a reproducible analytical framework.

The repository separates:

- source code,
- methodology documentation,
- data-source documentation,
- figures,
- derived results, and
- reproducibility instructions.

Detailed documentation is available in:

- [`docs/methodology.md`](docs/methodology.md)
- [`docs/data_sources.md`](docs/data_sources.md)
- [`docs/reproducibility.md`](docs/reproducibility.md)

---

## Citation

### Repository Citation

Until the official Springer DOI and final proceedings citation are available, please cite the repository as:

**Franklin, Victoria Love. (2026). _SEGDA: Socio-Environmental Grid Disruption Analysis — Reproducibility Repository_GitHub.**

Citation metadata are also provided in:

```text
CITATION.cff
```

### Forthcoming Springer Publication

Franklin, V. L. (2026). *Socio-Environmental Grid Disruption Analysis: A Multi-Scale Spatial Assessment of Energy Justice and Climate Resilience Across California Census Tracts and Counties, 2018–2023.* EAI SmartGIFT 2026. Springer LNICST. **DOI: Pending.**

This citation will be updated when Springer assigns the final DOI, volume, page numbers, and publication metadata.

---

## License

The **source code** in this repository is licensed under the **MIT License**, subject to the terms provided in the repository's `LICENSE` file.

Copyright © 2026 Victoria Love Franklin.

The MIT software license applies to the repository's source code and does **not** grant rights to the Springer-published version of the associated manuscript or other publisher-controlled materials.

The associated manuscript and publisher-formatted materials remain subject to the applicable EAI/Springer Nature publication and copyright terms.

Third-party datasets remain subject to the licenses, terms of use, and attribution requirements of their respective providers.

---

## Research Use

SEGDA is provided to support reproducibility, methodological transparency, academic research, and continued investigation into environmental justice, energy resilience, climate hazards, spatial inequality, and critical infrastructure resilience.

Users applying the framework to other geographic areas, time periods, or datasets should independently validate source-data definitions, geographic units, temporal coverage, normalization procedures, and analytical assumptions.

---

## Author

**Victoria Love Franklin**  
Ph.D. Data Science Research Scholar  
Published Research Author  

Research areas include artificial intelligence and machine learning, GIS and geospatial analytics, smart grids, grid resilience, critical infrastructure, cybersecurity, digital twins, environmental justice, climate resilience, public health, and biosurveillance.

---

## Repository Status

**SEGDA**

- Research framework: Complete
- Audited analytical pipeline: Complete
- EAI SmartGIFT 2026 paper: Accepted
- Springer LNICST proceedings publication: Pending
- Springer DOI: Pending
- Official Springer publication URL: Pending

This repository will be updated when the final publication metadata becomes available.
