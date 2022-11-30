# used_car_sales
A predictive analysis on used-car sales in the US

Link to Jupyter notebook with full analysis: 
https://github.com/purnamididuddi/used_car_sales/blob/main/used_car_analysis.ipynb


Excerpts of the analysis from the Jupyter notebook:
##### Many models were built in an effort to give best results to our customer. Below is a summary of each of their performance

| <span style='background:orange'>Model # | <span style='background:orange'>Model Description | <span style='background:orange'>Purpose | <span style='background:orange'># of Dimensions | <span style='background:orange'>Train/Dev/Test MAE | <span style='background:orange'>Model Score on Testset |
| :-: | :-: | :-: | :-: | :-: | :-: |
|<span style='background:yellow'> Model 1 | Linear regression | Baseline | 121 | 5234/5253/5214 | 71.90 |
|<span style='background:yellow'> Model 2 | Linear regr on scaled data | Effect of scaling | 121 | 5231/5250/5212 | 71.95 |
|<span style='background:yellow'> Model 3 | Scaling + 3rd order poly + Linear regr | Effect of adding polynomials | 128 | 4945/4957/4952 | 74.24 |
|<span style='background:yellow'> Model 4 | Scaling + 3rd order poly + Ridge regr | Effect of penalizing dimensions | 128 | 4954/4966/4963 | 74.08 |
|<span style='background:yellow'> Model 5 | Scaling + 3rd order poly + LASSO regr | Effect of penalizing dimensions | 76 (effective) | 4954/4966/4963 | 73.9 |
|<span style='background:yellow'> Model 6 | Scaling + 3rd order poly + LASSO selector + Linear regr | Feature selection using Lasso + Linear regression | 76 | 4959/4971/4968 | 74.14|

    
