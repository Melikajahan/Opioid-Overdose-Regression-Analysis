# County-level Data Provenance (South Carolina)

This document records the sources and preparation steps for the **county-level** datasets used in this repository. ZIP-level data are **not** distributed (see `zip_level/data/README.md`).

---

## 1) Opioid mortality (CDC WONDER)

- **Source:** Centers for Disease Control and Prevention, National Center for Health Statistics. *Multiple Cause of Death 2018–2023 on CDC WONDER Online Database*.
- **Use in this project:** Age-adjusted opioid overdose death rate per 10,000 population at the county level (South Carolina).
- **Accessed:** 2024-07-29
- **URL:** https://wonder.cdc.gov/wonder/help/mcd-expanded.html
- **Notes:** Followed CDC WONDER guidance on small-count suppression and standard rate interpretation.

**Suggested citation (BibTeX):**
    @report{cdc2024wonderdata,
      author       = {{Centers for Disease Control and Prevention, National Center for Health Statistics}},
      title        = {Multiple Cause of Death 2018--2023 on CDC WONDER Online Database},
      institution  = {{CDC WONDER}},
      year         = {2024},
      url          = {https://wonder.cdc.gov/wonder/help/mcd-expanded.html},
      note         = {Accessed 2024-07-29}
    }

---

## 2) Naloxone distribution centers (SC DHEC / ArcGIS Hub)

- **Source:** South Carolina Department of Health and Environmental Control (DHEC). *Naloxone Locations — SC DHEC [Map]* on ArcGIS Hub.
- **Use in this project:** Point locations of naloxone dispensing sites statewide.
- **Accessed:** 2024-07-29
- **URL:** https://arc-gis-hub-home-arcgishub.hub.arcgis.com/maps/13903a78e86048ceb05e4c16ce1f58dc/about
- **Processing:** Points were geocoded and aggregated to the county level using GIS software. To account for geographic variation in county size, the count of naloxone centers was normalized by land area and expressed as **centers per 1,000 square miles**.

**Suggested citation (BibTeX):**
    @misc{scdhec2024naloxonemap,
      author       = {{South Carolina Department of Health and Environmental Control}},
      title        = {Naloxone Locations -- SC DHEC [Map]},
      year         = {2024},
      url          = {https://arc-gis-hub-home-arcgishub.hub.arcgis.com/maps/13903a78e86048ceb05e4c16ce1f58dc/about},
      note         = {Accessed 2024-07-29}
    }

---

## 3) Socioeconomic & demographic indicators (ACS via ArcGIS Online)

- **Source:** U.S. Census Bureau. *ACS 2017–2021 Demographic and Housing Estimates — Census Tract Summary [Data set]* accessed via ArcGIS Online.
- **Use in this project:** Community-level socioeconomic and demographic variables aggregated and analyzed at the **county** level using the most recent estimates available for 2023.
- **Accessed:** 2024-07-29
- **ArcGIS item:** https://www.arcgis.com/home/item.html?id=ddd1510ed1964e2e8fb1ded93e9b03b1

**Suggested citation (BibTeX):**
    @misc{uscensus2024acs,
      author       = {{U.S. Census Bureau}},
      title        = {ACS 2017--2021 Demographic and Housing Estimates -- Census Tract Summary [Data set]},
      year         = {2024},
      howpublished = {\url{https://www.arcgis.com/home/item.html?id=ddd1510ed1964e2e8fb1ded93e9b03b1}},
      note         = {Accessed 2024-07-29}
    }

---

## Preparation summary (county level)

- **Aggregation**
  - Naloxone locations (points) aggregated to county; normalized to **centers per 1,000 sq mi**.
  - Socioeconomic/demographic indicators aggregated to county using the most recent available estimates (2023) from the ACS-derived dataset via ArcGIS Online.
  - Mortality rates taken as reported from CDC WONDER (age-adjusted, per 10,000).

- **Harmonization**
  - Datasets aligned to a common county geography for South Carolina.
  - Variable names standardized for analysis; units documented in the data dictionary.

> **Note:** ZIP-level datasets are confidential and are not included in this repository. Only county-level data and derived artifacts are shared here.

---

## Licensing & terms

- **Code:** Custom “view-only” license (see `LICENSE`).
- **County-level data:** Released under **CC BY 4.0** (see `DATA_LICENSE.md`).
- **Original sources:** Users must follow the terms and attribution requirements of CDC WONDER, SC DHEC, and the U.S. Census Bureau / ArcGIS Online.
