---
title: "House Pricing Predictor using Random Forest and Linear Regression"
excerpt: "Final submission for my Econ 21300 (Data Construction and Interpretation in Economic Applications) class with Steven Levitt. We used R to ingest data, clean it, and then do feature selection and validation testing to run My predictions were the second most accurate in the class, giving me an A"
collection: portfolio
---

[View Project on Github](https://github.com/diogoviveiros/ECON-21300-Final-Housing-Prediction)


This project was a part of my final in Econ 21300 "Data Construction and Interpretation in Economic Applications" with Steven Levitt, where we used R to investigate California housing prices, created OLS and Random Forest models, and then tried to validate these in order to create as accurate of a prediction as possible for the datasets where we did not have any pricing data. Our final grade was partly dependent on how accurate our prices were, and I had the 2nd best MSE in the class, giving me an A. 
Key Question

    What factors predict housing prices in California?

# Data Sources

   We received three data sets with pre-split housing data, two for testing and one for validation. These were provided by our class and as such I do not have a link to them, but I have put these CSVs on my Github repo.

# Data Cleaning 

  Extensive data cleaning was done. I removed:

  - 67 rows with missing values.
  - 97 rows with implausible prices (< $2,600 or -99).
  - Removed constant or meaningless columns like dwelling_units, above_3rd_floor_area.
  - Converted "yes"/"no" categorical variables into binary for OLS modeling.


# Methodology

  Feature selection was done in a three step process for OLS: 
  - **Multicollinearity checks:** First, I did multicollinearity filtering by calculating the Variance Inflation Factor for each feature. Any features that had a baseline value of 5 I simply kept. With other features that had higher values, I applied more observational and common sense methodologies. 
  - **Common sense feature removal:** By observing several features that had high collinearity, we can remove ones that make sense that they would be correlated. For example, I removed *shape_area* since we already have *shape_length* feature which had a lower VIF. Removing *shape_area* made *shape_length* have a VIF under 5, so it was kept. I did this process for a variety of features, such as:

| **Removed (High VIF)**    | **Removed Because:**                                        | **Instead Kept:**        | **Kept Because:**                                                             |
|---------------------------|-------------------------------------------------------------|--------------------------|-------------------------------------------------------------------------------|
| `shape_area`              | Highly correlated with `shape_length`                       | `shape_length`           | Measures parcel size but with less collinearity; still captures lot scale.    |
| `story_height`            | Correlated with multiple area features                      | `ground_floor_area`, `t2nd_floor_area`, `t3rd_floor_area` | These provide more direct and interpretable measurements of size per floor. |
| `effective_yr`            | Highly correlated with `construction_yr`                    | `construction_yr`        | Both reflect age; `construction_yr` is more transparent and interpretable.   |
| `dwelling_units`          | Constant value (1 for all rows), no variance                | *None (removed outright)*| Dropped due to zero variance — added no information to either model.         |
| `above_3rd_floor_area`    | Constant value (0 for all rows)                             | *None (removed outright)*| Dropped as it had no variation across observations.                          |
| `shape_area`, `lot_size` (potential conflict) | Potentially measuring similar land scale | `lot_size`               | `lot_size` may better capture usable land parcel, often more interpretable. |

  - **High P-Values:** After removing high VIF variables, I then focused on running the model several times in order to find values that had a P-Value greater than 0.05 and were therefore statistically insignificant.

  For Random Forest, I applied a sort of Grid Search methodology where I started by adding only the same variables I had for my OLS model. Then, I added additional features, reevaluating my MSE over time. With Random Forests, the mtry variable and the number of trees is also important, so I tried different models with different numbers of mtry and trees. Ultimately, I rested on a 500 tree limit with an mtry of 7 (7 variables allowed to be randomly selected per tree), and this seemed to give me the best benefits of performance to low MSE. 

# Key Findings
## OLS Regression
  - My Adjusted R² for this model was quite strong at 0.7154.
  - Statistically significant predictors included:
      - ground_floor_area (+$46.50/sq ft)
      - total_full_bath (+$8,590 per bath)
      - fireplace_openings
      - central_air
      - aquality_class.
   
  - Spatial features such as Dane_lat and Dane_long proved to be quite important, which makes sense. They had significant negative coefficients across all models. This suggests that homes located further south or west (coastal areas) tended to be more expensive.

## Random Forest

   Showed weaker performance in the distribution tails (underestimated high-end values), likely due to ensemble averaging behavior. Due to this, I decided to focus on the OLS model for my final prediction of the testing datasets. 

## Final Prediction

   I discovered that homes with ≥3 full bathrooms had a price floor (~$300K). As such, for increased accuracy, I decided to split the testing dataset into two subgroups:
   - Less than 3 bathrooms: modeled with standard regression.
   - ≥3 bathrooms: modeled with a targeted higher-end regression.

   This hybrid approach substantially improved tail-end accuracy and resulted in a more realistic distribution match with the training set.

[You can view my full output on my Github here](https://github.com/diogoviveiros/ECON-21300-Final-Housing-Prediction/blob/main/Project_4.pdf)
