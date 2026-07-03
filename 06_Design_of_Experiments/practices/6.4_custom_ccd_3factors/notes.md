# 6.4 Analyzing a Custom Central Composite Design

## Objective
Fit a full second-order polynomial model to a central 
composite design and identify the optimal conditions 
to maximize Yield.

## Dataset
File: Custom CCD 3 Factors.jmp

## Factors and Response

| Factor | Low | High |
|--------|-----|------|
| Catalyst | 1 | 5 |
| Temperature | 50 | 120 |
| Time | 4 | 24 |

Response: Yield
Goal: Maximize

## Data Table
<img width="1152" height="729" alt="64_ccd_data" src="https://github.com/user-attachments/assets/f9534be8-7c85-4e6e-86a7-279e7e453e8f" />


## Initial Analysis
<img width="1152" height="729" alt="64_initial_analysis" src="https://github.com/user-attachments/assets/73c60a65-c693-41d6-8efe-087b40c15082" />


The model was fit using Analyze, Fit Model with the 
Response Surface macro applied to all three factors. 
This added all main effects, two-way interactions, 
and quadratic terms to the model automatically.

## Questions and Solutions

**Q1. Is there evidence of lack of fit?**

No. The p-value for lack of fit is 0.2001, which is 
greater than 0.05. There is no evidence of lack of 
fit. The model adequately describes the relationship 
between the factors and the response.

**Q2. Which three effects are most significant?**

| Rank | Term | P-Value |
|------|------|---------|
| 1 | Temperature | 0.00000 |
| 2 | Temperature × Time | 0.00000 |
| 3 | Temperature × Temperature | 0.00000 |

**Q3. What are the optimal factor settings?**

## Prediction Profiler
<img width="1152" height="729" alt="64_prediction_profiler" src="https://github.com/user-attachments/assets/3f84f995-b2e2-438b-9252-76dad9402700" />

Using Maximize Desirability in the Prediction Profiler:

| Factor | Optimal Setting |
|--------|----------------|
| Catalyst | 3.4 |
| Temperature | 118.8 |
| Time | 4 (low) |

Predicted Yield = 93.75%
95% Confidence Interval: [91.90, 95.61]
Desirability = 0.998

**Q4. What does the Response Surface solution suggest?**

## Response Surface
<img width="1152" height="729" alt="64_response_surface" src="https://github.com/user-attachments/assets/f8583978-7251-45ab-b0af-9fdc41c8d076" />



The Response Surface solution identifies critical 
values outside the experimental range:

| Factor | Critical Value | Experimental Range |
|--------|---------------|-------------------|
| Temperature | 124.1 | 50 to 120 |
| Time | 0.53 | 4 to 24 |

This suggests that even higher Yield may be achievable 
at Temperature above 120 and Time below 4. A 
confirmation trial at both the Prediction Profiler 
optimum and the Response Surface solution settings 
would be a logical next step.

## Key Takeaways

A central composite design enables the estimation of 
quadratic effects, making it possible to model 
curvature in the response surface. When the Response 
Surface solution falls outside the experimental range, 
it indicates that the true optimum may lie beyond 
the current design space. Sequential experimentation 
allows you to follow up with additional runs in the 
direction of the optimum.
