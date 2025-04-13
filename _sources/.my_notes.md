# Some notes on CPH model


## What is the p-value in summary?
In a Cox Proportional Hazards model summary, the p-value next to coefficients indicates:

- The statistical significance of each predictor variable in the model
- It tests the null hypothesis that the coefficient (β) equals zero (no effect)
- Small p-values (typically < 0.05) suggest strong evidence against the null hypothesis, indicating the predictor has a significant effect on survival

The p-value is calculated using:

- The Wald test statistic, which is the coefficient divided by its standard error
- This test statistic follows a standard normal distribution under the null hypothesis

When interpreting Cox model results:

- P-value < 0.05: The variable is considered statistically significant
- P-value ≥ 0.05: Insufficient evidence to conclude the variable affects survival

However, p-values should not be the only criterion for variable selection, as clinical or practical significance should also be considered.

## Calculating p-value in CPH
The calculation of p-values in Cox models involves several steps:

1. Calculate the Wald test statistic (z):
    - z = β̂ / SE(β̂)
    - where β̂ is the estimated coefficient
    - SE(β̂) is the standard error of the coefficient
2. The standard error is derived from:
    - The inverse of the negative Hessian matrix (information matrix)
    - This matrix contains second partial derivatives of the log partial likelihood
3. Convert the Wald statistic to a p-value:
    - Using the standard normal distribution (z-distribution)
    - P-value = 2 × P(Z > |z|) for a two-sided test
    - Where Z follows a standard normal distribution

The Wald test is just one approach - alternatives include the likelihood ratio test and score test, which may be more appropriate in certain situations, particularly with small sample sizes.


## P-values in Predictive Modeling vs. Statistical Inference

When building predictive models, relying solely on p-values for variable selection has several limitations:

- P-values are designed for statistical inference, not prediction - they measure statistical significance but not predictive power
- Variables with high p-values might still improve predictive performance in combination with other features
- P-values are sensitive to sample size - with large datasets, even tiny effects can be statistically significant

Better approaches for predictive model variable selection include:

- Cross-validation performance metrics
- Feature importance measures (e.g., permutation importance)
- Domain expertise and practical significance
- Regularization techniques (Lasso, Ridge, Elastic Net)

For survival analysis specifically, consider using:

- Harrell's C-index for assessing predictive discrimination
- Time-dependent ROC curves and AUC
- Integrated Brier Score for overall prediction accuracy

The best practice is to combine multiple criteria rather than relying on any single measure for feature selection in predictive modeling.

## nterpreting Categorical Variables in Cox Models

When dealing with categorical variables with 3 or more levels in a Cox model:

- The model creates dummy variables using one level as the reference category
- Each non-reference category gets its own coefficient in the model output
- The hazard ratio for each coefficient represents the risk compared to the reference category

For example, if you have a variable "Education" with levels "High School", "Bachelor's", and "Graduate":

- If "High School" is the reference category, you'll see two coefficients in the output:
    - Bachelor's vs. High School
    - Graduate vs. High School

Interpretation example:

- If the hazard ratio for "Bachelor's" is 1.5 (p < 0.05), this means:
    - The hazard (risk of event) is 50% higher for those with Bachelor's compared to High School
    - This difference is statistically significant

Key considerations:

- The choice of reference category can affect interpretation
- Overall significance of the categorical variable can be tested using likelihood ratio tests
- Visual plots can help understand the relative risks across all categories
