# Opioid Overdose Regression Analysis – South Carolina

This repository contains two related statistical and spatial regression analyses at **county** and **ZIP** levels, investigating the relationship between opioid overdose outcomes and factors such as **naloxone access**, **socioeconomic indicators**, and **demographics** in South Carolina.

## Project Overview
The project explores:
- Impact of naloxone distribution (counts & proximity) on overdose mortality (county) and opioid-related ED visits (ZIP)
- Influence of community-level socioeconomic and demographic factors
- Spatial dependencies in overdose outcomes

## Repository Structure
```plaintext
opioid-overdose-regression-analysis/
│
├── county_level/       # County-level regression data
│  ├─ data/
│  │  ├─ raw/          
│  │  ├─ processed/    
│  │  └─ dictionary/  
├── zip_level/          
├── docs/               # Reports, visualizations, and summaries
├─ data-provenance/
│  └─ PROVENANCE.md
├── LICENSE             # Custom license for viewing only
├── README.md           # Main project overview
└──DATA_LICENSE.md
```


## Methods & Models
- **County-Level**: OLS with full diagnostics, Poisson & Negative Binomial Regression, Spatial Error (SEM) and Spatial Lag (SLM) Models
- **ZIP-Level**: Poisson & Negative Binomial Regression, Spatial Lag/Durbin Models
- **Diagnostics**: Linearity, homoscedasticity, residual normality, multicollinearity (VIF), Moran’s I
- **Model Comparison**: AIC/BIC, R², log-likelihood, residual plots

## Key Features
- Multiple naloxone measures: center counts, distances from centroids (10, 20, 30 miles), closest/average distances
- Buprenorphine provider counts as a treatment access proxy
- Rich set of socioeconomic & demographic variables

## Data
- **County-level (open):** Included under `county_level/data/` with a separate data license (**CC BY 4.0**, see `DATA_LICENSE.md`). Detailed source attribution in `data-provenance/PROVENANCE.md`.

- **ZIP-level (restricted):** **Not included** due to confidentiality. The folder `zip_level/data/` contains a README describing required file names/columns for local reproduction. Synthetic schemas may be provided for structure only (no real values).
> Note: This repository’s *code* remains under a custom “view-only” license (see `LICENSE`). County-level *data* are separately licensed.

### County-level data (files)
 - [`Edited_Dataset.csv`](county_level/data/raw/Edited_Dataset.csv) — raw input
 - [`county_master.csv`](county_level/data/processed/county_master.csv) — processed canonical copy
 - [`county_dictionary.csv`](county_level/data/dictionary/county_dictionary.csv) — column dictionary

## Tech Stack
- Python: `pandas`, `numpy`, `statsmodels`, `geopandas`, `PySAL`
- GIS processing in ArcGIS

## Key Findings (High-Level)
- Naloxone access has a consistent, significant impact on reducing opioid overdose deaths (county level) and opioid-related ED visits (ZIP level).
- County-level analysis:
  * Higher rates of naloxone centers per 1,000 square miles are strongly associated with lower death rates.
  * Spatial Durbin Models capture regional spillover effects — areas benefit from neighboring counties’ naloxone availability.
  * Proportion of White Population is positively associated with death rates when controlling for other factors.
- ZIP-level analysis:
  * Center count is positively associated with ED visits (reflecting targeting toward high-need areas).
  * Distance-based measures show a negative association — closer proximity to naloxone centers correlates with fewer ED visits.
- Policy implications:
  * Distance-based planning can better target underserved areas.
  * Regional strategies are more effective than isolated local interventions.
  * Accessibility and equity in naloxone distribution remain critical for harm reduction.

## License
This project is protected under a custom license.  
You are welcome to **view the code** for personal, educational, or evaluation purposes.  
However, **copying, reproducing, modifying, or using** this code without prior written permission from the author is strictly prohibited.  

Collaboration and contributions are welcome but must be discussed in advance.  
📩 Contact: [jahanmelika@gmail.com or www.linkedin.com/in/melika-jahan-beikloo]
