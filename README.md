# Opioid Overdose Regression Analysis – South Carolina

This repository supports the manuscript:

**A Typology Based on Naloxone Availability, Opioid Overdose Mortality, and Emergency Department Visits in South Carolina**

The study examines geographic variation in opioid overdose burden and naloxone access in South Carolina using county-level and ZIP-level analyses. The repository includes shareable county-level data, code structure, data documentation, selected derived outputs, and reproducibility notes. ZIP-level data are not publicly shared because the ZIP-level analytic dataset includes restricted health outcome data and non-public demographic, socioeconomic, community, and naloxone-access data that are not suitable for open posting under the project’s data-use and confidentiality constraints.

## Repository Purpose

This repository is intended to support transparency and reproducibility for the manuscript by providing:

- Shareable county-level data and documentation
- Code used for regression, spatial diagnostics, and burden–access typology development
- Data provenance and variable definitions
- Selected derived outputs such as tables, figures, maps, and typology summaries
- Documentation for the restricted ZIP-level analysis workflow without releasing non-public or restricted ZIP-level data values

## Study Overview

The analysis was conducted at two geographic scales:

1. **County level**
   - Outcome: age-adjusted opioid overdose death rate per 10,000 population
   - Main modeling approach: spatial regression, with emphasis on the Spatial Error Model (SEM) after testing for spatial dependence
   - Access measure: naloxone distribution center density per 1,000 square miles
   - Additional covariates: socioeconomic, demographic, healthcare access, and treatment access variables

2. **ZIP code level**
   - Outcome: average annual opioid-related emergency department visits
   - Main modeling approach: Negative Binomial regression due to overdispersed count data
   - Access measures: naloxone center counts and proximity-based measures
   - Additional covariates: socioeconomic, demographic, rurality, healthcare access, and treatment access variables
   - Data availability: ZIP-level analytic data are restricted or non-public and are not included in this repository

The study also develops burden–access typologies to identify areas with relatively high opioid burden and relatively low naloxone access.

## Repository Structure

```plaintext
opioid-overdose-regression-analysis/
│
├── county_level/
│   ├── data/
│       ├── raw/              # Shareable county-level input data
│       ├── processed/        # Processed county-level analysis data
│       └── dictionary/       # County-level variable dictionary
│
├── zip_level/
│   ├── data/
│       └── README.md         # Restricted-data note and expected schema
│
├── typology/
│   └── outputs/              # Typology tables, maps, and summary figures
│
├── docs/
│   ├── figures/              # Selected manuscript figures and map outputs
│   └── tables/               # Shareable result tables
│
├── data-provenance/
│   └── PROVENANCE.md         # Data sources and processing notes
│
├── DATA_LICENSE.md           # License for shareable data
├── LICENSE                   # License for code and repository materials
└── README.md
