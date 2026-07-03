# 6.3 Analyzing a 20 Run Custom Design

## Objective
Analyze a 20-run optimal custom design to identify 
the factor settings that maximize percent reacted 
in a chemical reactor.

## Dataset
File: Reactor 20 Custom.jmp

## Factors and Response

| Factor | Low | High |
|--------|-----|------|
| Feed Rate | 10 | 15 |
| Catalyst | 1 | 2 |
| Stir Rate | 100 | 120 |
| Temperature | 140 | 180 |
| Concentration | 3 | 6 |

Response: Percent Reacted
Goal: Maximize

## Data Table
<img width="1152" height="729" alt="63_reactor20_data" src="https://github.com/user-attachments/assets/26548aa6-3519-4a1e-9a6e-1c7517cbc3d5" />


## Initial Model
<img width="1152" height="729" alt="63_initial_model" src="https://github.com/user-attachments/assets/0cdf593c-7153-42fd-921c-932960d083b6" />


## Reduced Model
<img width="1152" height="729" alt="63_reduced_model" src="https://github.com/user-attachments/assets/05c706cc-0c50-4fd1-97d6-85d2a9f9b73e" />


## Questions and Solutions

**Q1. Which terms are significant at the 0.05 level?**

| Term | P-Value |
|------|---------|
| Catalyst | 0.00057 |
| Catalyst × Temperature | 0.00372 |
| Temperature | 0.00511 |
| Temperature × Concentration | 0.00734 |
| Concentration | 0.03291 |

**Q2. How many terms are in the reduced model?**

The reduced model contains five terms: three main 
effects (Catalyst, Temperature, Concentration) and 
two two-way interactions (Catalyst × Temperature 
and Temperature × Concentration).

Model fit improved after reduction:
RMSE: 4.239 → 2.9795
R²: 0.6812 → 0.97

**Q3. What factor settings maximize Percent Reacted?**

## Prediction Profiler
<img width="1152" height="729" alt="63_prediction_profiler" src="https://github.com/user-attachments/assets/6b1c06c7-4b0f-4d78-bcb2-abcbe38b13b2" />


Using Maximize Desirability in the Prediction Profiler:

| Factor | Optimal Setting |
|--------|----------------|
| Catalyst | 2 (high) |
| Temperature | 180 (high) |
| Concentration | 3 (low) |
| Feed Rate | Not significant |
| Stir Rate | Not significant |

Predicted Percent Reacted = 95.23%
95% Confidence Interval: [91.37, 99.08]
Desirability = 0.730

**Q4. What does the confidence interval represent?**

The bracketed values [91.37, 99.08] represent a 95% 
confidence interval for the mean Percent Reacted at 
the optimal factor settings. Assuming the process is 
stable and other factors are controlled, the true 
mean response is expected to fall within this range.

## Key Takeaways

Custom designs provide flexibility when classical 
fractional factorial designs do not fit the 
experimental constraints. Feed Rate and Stir Rate 
were found to be nonsignificant and were removed 
from the model, allowing resources to focus on 
the three factors that truly drive reactor output. 
The interaction between Catalyst and Temperature 
highlights that these two factors must be considered 
together rather than independently.
