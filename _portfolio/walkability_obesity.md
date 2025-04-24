---
title: "Walkability and Obesity Analysis"
excerpt: "Regression analysis of walkability's impact on obesity across U.S. counties<br/><img src='/images/500x300.png'>"
collection: portfolio
---
This project explores whether the EPA's National Walkability Index can predict obesity rates when controlling for socioeconomic and access-related variables.

**Key Question**
> Does walkability predict obesity rates when adjusting for other factors?

**📊 Data Sources**
- **EPA SMART Location Database** (walkability, job access, land use)
- **CDC PLACES** (obesity, healthcare access)
Merged by county FIPS codes.

**Methodology**
Multivariate OLS regression with controls for:
- Healthcare access (`ACCESS2_AdjPrev`)
- Population size (`TotalPopulation`)
- Job accessibility (`Ac_Total`, `Ac_Unpr`)
- Demographics (`Pct_AO0`)
- Income (`R_PCTLOWWAGE`)
- Walkability (`NatWalkInd`)

**📍 About NatWalkInd**
EPA's composite walkability score (0–20) including:
- Street connectivity
- Land use diversity
- Transit proximity

**📈 Key Findings**
- Adjusted R² = 0.385
- `NatWalkInd` statistically significant (p < 0.001)
- Coefficient = -0.8663: A 1-point rise in walkability reduces obesity by ~0.87 percentage points
