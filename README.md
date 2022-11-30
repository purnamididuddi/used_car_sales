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

    
An attempt was made to reduce features using SequentialFeatureSelection, but it was a very time consuming activity given there are 128 dimensions for it to work on. 
    
##### In my opinion, model 6 is the best bet with reduced dimensions and on-par best score
    

#### <ins>Evaluation</ins>
While our best model so far have performed reasonably OK, there are still some predictions giving negative values.

As a next step, we should fine-tune the model even further. One option I could think of is to build separate models for high priced cars and low priced cars. This might reduce the overall error on individual models.

For now, we will continue with gathering insights from our best model at this point.
    
    
We can see that Year, type, Odometer, manufacturer and fuel-type are important factors influencing used-car sales.

The correlation matrix tells Year and Price are positively correlated while Odometer and Price are negatively correlated.

From this fact, we can safely infer that:

Higher the year (meaning, more recent the car), better the price.
Lower the odometer reading, higher the price.
A next step is to understand how to interpret permutation importance of a categorical variable (for ex: perm importance of 'type' is 0.202: What does this mean? which type is the best driver?)
    

### Report to client (used-car dealers)
1. Cars whose manufactured year is more recent have better prospects of selling for higher price

2. Also, cars with lower Odometer reading have better prospects of selling for higher price

3. The title_status and transmission-type are not that important for the buyers. So, if (1) and (2) are satisfied, the dealer can stock up the car regardless of the title_status and transmission-type
    