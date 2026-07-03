# 6.3 Designing a Fractional Factorial Experiment

## Objective
Design a screening experiment to study five continuous 
factors using a fractional factorial design, within a 
budget of 20 total runs.

## Factors and Response

| Factor | Low | High |
|--------|-----|------|
| X1 | −1 | 1 |
| X2 | −1 | 1 |
| X3 | −1 | 1 |
| X4 | −1 | 1 |
| X5 | −1 | 1 |

Response: Y
Goal: Maximize

## Design Setup
<img width="1152" height="729" alt="63_screening_design_list" src="https://github.com/user-attachments/assets/5a977ce2-6327-4352-a5aa-4ec321190d26" />

The experiment was designed using the Screening 
platform in JMP under DOE, Classical. Five continuous 
factors were entered and a list of candidate designs 
was reviewed.

## Aliasing Structure
<img width="1152" height="729" alt="63_aliasing_effects" src="https://github.com/user-attachments/assets/9a3c8c63-e2e5-41f1-a31f-f563b951459c" />


## Design Table
<img width="1152" height="729" alt="63_fractional_design_table" src="https://github.com/user-attachments/assets/0f97178e-10af-4ff1-8b98-5001cedf8ab1" />


## Model Specification
<img width="1152" height="729" alt="63_model_specification" src="https://github.com/user-attachments/assets/7009493b-2e18-4638-bb9b-b15d1ef7bc19" />


## Questions and Solutions

**Q1. What are the candidate screening designs 
within 20 runs?**

| Runs | Design Type | Resolution |
|------|-------------|------------|
| 8 | Fractional Factorial (2⁵⁻²) | 3 — Main Effects Only |
| 12 | Plackett-Burman | 3 — Main Effects Only |
| 16 | Fractional Factorial (2⁵⁻¹) | 5 — All 2-factor interactions |

The 32-run full factorial was excluded as it exceeds 
the budget of 20 runs. Blocked designs were also 
excluded as blocking was not required.

**Q2. Which effects are aliased in the 2⁵⁻¹ design?**

No main effects or two-way interactions are aliased 
with other main effects or two-way interactions. This 
means all main effects and two-way interactions can 
be estimated independently.

**Q3. How many runs are in the final design?**

The final design contains 20 runs: 16 factorial 
points and 4 center points.

2⁵⁻¹ = 2⁴ = 16 factorial points
16 + 4 center points = 20 total runs

**Q4. What do the center points represent?**

Center points set every factor simultaneously to the 
midpoint between its low and high values, coded as 0. 
In this design, all five factors are set to 0 for each 
center point run, represented by the pattern 00000.

Center points serve two purposes. They provide 
replication for estimating experimental error, and 
they allow a lack of fit test to determine whether 
the linear model adequately describes the relationship 
between the factors and the response.

**Q5. Which effects can be estimated?**

The model includes all five main effects and all ten 
two-way interactions, for a total of 15 estimable 
effects plus the intercept and block term.

## Key Takeaways

Fractional factorial designs make it possible to study 
many factors efficiently by running only a fraction of 
the total treatments. The 2⁵⁻¹ design cuts the full 
32-run experiment in half while still allowing all main 
effects and two-way interactions to be estimated 
independently. Adding center points to the design 
provides an estimate of experimental error and the 
ability to detect curvature, which serves as a 
diagnostic for whether a more complex model is needed.
