# Prescriptive Survival Analysis

This type of analytics answer the question "what should be done?"

```{note}
This chapter is out of the scope of this tutorial and most of the contents are under preparation. 
Upon interest below topics are relevant to prescriptive survival analysis 
```

## Introduction to Causal Inference (CI)
There are two schools of thought in Causal Inference. 

1. Potential Outcome

2. Structural Causal Models 


```{seealso}
The Causal Inference school of thoughts are extensively covered in below talks   

- [Causal Inference: a deep dive | Data Science in Finance 2024](https://www.youtube.com/watch?v=XTn3Fn-pt3s)

- [Causal Effect Estimation in Practice: Lessons Learned from E-commerce & Banking | PyData Amsterdam 2024](https://www.youtube.com/watch?v=pz7QD2GPBlE)
```


## Applying CI tools to Survival Analysis

1. Potential Outcome: 

   - Calculate the propensity score given relevant variables
   - Correcting for unbalanced confounding using the Inverse Propensity Weights to re-weight Kaplan-Meier (KM) estimator. 

2. Structural Causal Models: Given the desired variable for effect estimation  

   - Identify the causal graph
   - Fit a Cox proportional hazard with only confounders (avoid including mediator & Collider)
   - Ensure the cox proportional hazard assumption is satisfied 
   - Average Treatment Effect (ATE) is the coefficient of the desired variable i.e., treatment 

```{note}

Checking cox proportional hazard assumption is not important for predictive analytics, while 
the situation is different in prescriptive analytics. 

- In prediction the objective is to maximize an accuracy metric, and not to learn about how individual feature contribute to the model making that prediction.

- In prescriptive analytics, the focus is to understand the influence of individual variables on the survival duration & event.

```

## Checking & Ensuring Proportional Hazard Assumption  

Under preparation

