---
title: "Analysis of County Walkability Ratings on Obesity Outcomes"
excerpt: "Regression analysis of walkability's impact on obesity across U.S. counties<br/>"
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
A multivariate Ordinary Least Squares (OLS) regression model was used to test how walkability affects obesity, adjusting for:

| Variable           | Description                              | Control Purpose                                         |
|--------------------|------------------------------------------|----------------------------------------------------------|
| `ACCESS2_AdjPrev`  | % without health insurance               | Controls for disparities in healthcare access            |
| `TotalPopulation`  | County population                        | Proxy for urban vs rural context                         |
| `Ac_Total`         | Total job accessibility                  | Reflects economic development and opportunity            |
| `Ac_Unpr`          | Access to unprotected/unstable jobs      | Captures economic vulnerability                         |
| `Pct_AO0`          | Demographic group %                      | Adjusts for demographic variation in obesity risk        |
| `R_PCTLOWWAGE`     | % earning low wages                      | Controls for income-related health disparities           |
| `NatWalkInd`       | National Walkability Index               | **Primary variable of interest**                         |

**📍 What is NatWalkInd?**  
The **National Walkability Index** is a composite EPA score (0–20 scale) that measures:
- Street connectivity (intersection density)  
- Land use diversity  
- Transit proximity  

Higher scores = greater walkability.

**📈 Key Findings**  
- Adjusted R² = 0.385 — the model explains ~38.5% of variance in obesity rates.  
- **Walkability (`NatWalkInd`) was statistically significant** (p < 0.001).  
- **Coefficient = -0.8663**: Each 1-point increase in walkability lowers obesity by ~0.87 percentage points.

[View Project on Github](https://github.com/diogoviveiros/Walkability-vs-Obesity)
