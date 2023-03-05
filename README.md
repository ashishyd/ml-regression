# ml-regression

`Constant` in regression analysis is referred to the point line cuts the **Y-axis**

`Backward Elimination` is irrelevant in Python, because the `Scikit-Learn library` automatically takes care of selecting the statistically significant features when training the model to make accurate predictions.

The linear based regression models are calculated with OLS (Ordinary Least Squares)
``` 
^β = (XTX)−1XTy

^β = ordinary least squares estimator
X = matrix regressor variable X
T = matrix transpose
y = vector of the value of the response variable
```
Support Vector Regression (SVR)
f ( x ) = ∑ n = 1 N ( α n − α n * ) G ( x n , x ) + b 

## Building a model

### Backward Elimination

**Step 1**: Select a significance level to stay in the model (e.g. SL = 0.05) or 5%

**Step 2**: Fit the model with all possible predictors

**Step 3**: Consider the predictor with the <ins>highest</ins> P-value. If P > SL, go to STEP 4, otherwise got to FIN (FINISH)

**Step 4**: Remove the predictor

**Step 5**: Fit model without this variable*

### Forward Elimination

**Step 1**: Select a significance level to enter the model (e.g. SL = 0.05) or 5%

**Step 2**: Fit all simple regression model y ~ x<sub>n</sub> Select the one with lowest P-value

**Step 3**: Keep this variable and fit all possible models with one extra predictor added to the one(s) you already have

**Step 4**: Consider the predictor with the <ins>lowest</ins> P-value. If P < SL, go to STEP 3, otherwise got to FIN (keep the previous model)

### Bidirectional Elimination (Stepwise Regression)

**Step 1**: Select a significance level to enter and to stay in the model (e.g. SLENTER = 0.05, SLSTAY = 0.05) or 5%

**Step 2**: Perform the next step of Forward Elimination (new variables must have: P < SLENTER to enter)

**Step 3**: Perform the next step of Backward Elimination (new variables must have: P < SLSTAY to stay)

**Step 4**: No new variables can enter and no old variables can exit then FIN

### All Possible Models

**Step 1**: Select a criterion of goodness of fit (e.g. Akaike Criterion)

**Step 2**: Construct all possible regression models: 2<sup>N</sup>-1 total combinators

**Step 3**: Select the one with best criterion, then FIN
