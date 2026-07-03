# 6.2 Analyzing a Replicated Full Factorial Experiment

## Objective
Analyze a replicated full factorial experiment with 
four factors to identify which factors significantly 
affect particle count and determine the optimal 
settings to minimize particles.

## Dataset
File: Particles 2.jmp

## Factors and Response

| Factor | Type | Low | High |
|--------|------|-----|------|
| Bath Time | Continuous | 10 | 20 hours |
| % Solution | Continuous | 5 | 15 |
| Rinse Time | Continuous | 1 | 5 hours |
| Type | Categorical | A | B |

Response: Particles (particles/cm²)
Goal: Minimize

## Design Table
<img width="1152" height="729" alt="62_particles2_data" src="https://github.com/user-attachments/assets/4f41261a-6754-4168-bd93-bebf91814a8d" />


## Initial Analysis
<img width="858" height="534" alt="62_initial_analysis" src="https://github.com/user-attachments/assets/c46c4b3c-ae2d-4214-a704-2b561aa355dd" />


The initial model included all four main effects and 
six two-way interactions. Backward elimination was 
used to reduce the model by removing the least 
significant terms one at a time, keeping all terms 
with a p-value of 0.05 or less.

## Reduced Model
<img width="1152" height="729" alt="62_reduced_model" src="https://github.com/user-attachments/assets/18b46a26-5df4-48c3-8eae-66df00555ebe" />

## Questions and Solutions

**Q1. How many main effects and two-way interactions 
are in the model?**

There are 4 main effects and 6 two-way interactions, 
giving 10 estimable effects in the full model.

**Q2. Which three effects are most significant?**

| Rank | Term | P-Value |
|------|------|---------|
| 1 | Bath Time | 0.00000 |
| 2 | % Solution × Rinse Time | 0.00001 |
| 3 | Rinse Time | 0.00027 |

**Q3. What terms remain in the reduced model?**

After removing all nonsignificant terms, the reduced 
model contains five terms:

- Bath Time
- % Solution × Rinse Time interaction
- Rinse Time
- Bath Time × % Solution interaction
- % Solution

**Q4. What factor settings minimize Particles?**
## Prediction Profiler
<img width="1152" height="729" alt="62_prediction_profiler" src="https://github.com/user-attachments/assets/2893e85b-8da4-428c-bbed-e3bc82adb92e" />


Using Maximize Desirability in the Prediction Profiler:

| Factor | Optimal Setting |
|--------|----------------|
| Bath Time | 20 hours (high) |
| % Solution | 5 (low) |
| Rinse Time | 5 hours (high) |

Predicted Particles = 0.998 particles/cm²

## Key Takeaways

The interaction between % Solution and Rinse Time was 
one of the most significant effects in the model. This 
means the effect of Rinse Time on particle count 
depends on the level of % Solution. This type of 
relationship cannot be detected with one-factor-at-a-
time experimentation. Factorial designs are essential 
for uncovering interactions between factors.
