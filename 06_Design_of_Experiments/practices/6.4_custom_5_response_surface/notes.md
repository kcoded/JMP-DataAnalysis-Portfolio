# 6.4 Analyzing a Custom Response Surface Design

## Objective
Analyze a 22-run custom response surface design with 
five factors to identify the settings that maximize 
Yield.

## Dataset
File: Custom 5 Response Surface.jmp

## Factors and Response

| Factor | Low | High |
|--------|-----|------|
| Volume | 1.5 | 10 |
| Catalyst | 1 | 5 |
| Temperature | 50 | 120 |
| Time | 4 | 24 |
| Sodium Acetate | 1.5 | 4 |

Response: Yield
Goal: Maximize

## Data Table
<img width="1152" height="729" alt="64_custom5_data" src="https://github.com/user-attachments/assets/ac298e78-b8de-4bf5-b4d1-153e98c07b2e" />


## Initial Model
<img width="1152" height="729" alt="64_initial_model" src="https://github.com/user-attachments/assets/afa1e183-e1da-4f6b-83a2-1aba3a32db95" />


## Reduced Model
<img width="1152" height="729" alt="64_reduced_model" src="https://github.com/user-attachments/assets/3395b846-9d47-4dc5-b121-9b85fb24046e" />


## Questions and Solutions

**Q1. Which terms are in the reduced model?**

After removing all nonsignificant terms one at a time, 
the reduced model contains nine terms:

- Temperature
- Temperature × Time
- Temperature × Temperature
- Volume
- Volume × Volume
- Time × Time
- Time
- Catalyst × Catalyst
- Catalyst

**Q2. Do the diagnostic plots reveal any issues?**

<img width="1152" height="729" alt="64_actual_predicted" src="https://github.com/user-attachments/assets/35a6494b-d252-46fc-9224-ad672742b27f" />

<img width="1152" height="729" alt="64_residual_plot" src="https://github.com/user-attachments/assets/4596d9c2-833e-4e0b-ab19-3b9f47af92d1" />

<img width="1152" height="729" alt="64_studentized_residuals" src="https://github.com/user-attachments/assets/ce5855ad-b855-4a81-9f9b-fa04efd470ec" />


No unusual patterns or outliers were identified. 
The points in the Actual by Predicted plot fall 
tightly along the diagonal line, indicating an 
excellent model fit (R² = 0.9994, RMSE = 0.7777). 
The Residual by Predicted plot shows random scatter 
around zero with no systematic patterns. All 
studentized residuals fall within the individual 
limits, confirming there are no outliers.

**Q3. What are the optimal factor settings?**

Using Maximize Desirability in the Prediction Profiler:

| Factor | Optimal Setting |
|--------|----------------|
| Volume | 3.66 |
| Catalyst | 3.37 |
| Temperature | 116.51 |
| Time | 4 (low) |
| Sodium Acetate | Not significant |

Predicted Yield = 95.31%
95% Confidence Interval: [94.11, 96.50]
Desirability = 0.971

## Key Takeaways

Sodium Acetate was found to be nonsignificant and 
was removed from the model entirely. The quadratic 
effects for Volume, Temperature, Time, and Catalyst 
were all significant, confirming that curvature is 
present in the response surface. A custom response 
surface design made it possible to estimate all of 
these effects efficiently in just 22 runs, compared 
to the much larger classical designs that would have 
been required for five factors.
