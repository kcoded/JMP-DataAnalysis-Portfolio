# 6.5 Anodize Case Study

## Objective
Analyze a multi-response experiment on an anodizing 
process and identify the factor settings that 
simultaneously satisfy all response goals. Use 
simulation to estimate the predicted defect rate 
under different levels of process variation.

## Dataset
File: Anodize.jmp

## Factors

| Factor | Low | High | Units |
|--------|-----|------|-------|
| Anodize Temp | 60 | 90 | °C |
| Anodize Time | 20 | 40 | min |
| Acid Conc | 170 | 205 | g/L |
| Dye pH | 5 | 6.5 | |
| Dye Conc | 10 | 15 | g/L |

## Responses

| Response | Goal |
|----------|------|
| Thickness | Maximize |
| L* | Match Target (10) |
| a* | Minimize |
| b* | Match Target |

## Reduced Model
<img width="1152" height="729" alt="65_reduced_model" src="https://github.com/user-attachments/assets/36f2818d-d795-4394-8b46-f9c87190b58d" />


## Initial Prediction Profiler
<img width="1152" height="729" alt="65_profiler_initial" src="https://github.com/user-attachments/assets/7c4855e3-c398-429d-ab15-74816ee5ac16" />


## Questions and Solutions

**Q1. Which effects are in the reduced model for a*?**

The reduced model for a* contains five main effects:
Anodize Temp, Anodize Time, Dye pH, Acid Conc, 
and Dye Conc. No interaction terms were retained.

**Q2. What are the starting values and predicted 
responses in the Profiler?**

The starting value for Acid Conc is 187.5, which is 
the midpoint of its experimental range (170 to 205). 
The predicted Thickness at the starting values is 
0.744. The bracketed values [0.7327, 0.7555] 
represent a 95% confidence interval for the mean 
Thickness at these factor settings.

**Q3. What is the response goal for L*?**
## Response Goal
<img width="1152" height="729" alt="65_response_goal" src="https://github.com/user-attachments/assets/03576668-2007-4fac-b888-1da2946cdd03" />


| Setting | Value |
|---------|-------|
| Goal | Match Target |
| Target | 10 |
| Lower Limit | 8 |
| Upper Limit | 12 |

**Q4. What is the optimal setting for Anodize Time?**
## Optimal Setting
<img width="1152" height="729" alt="65_profiler_optimal" src="https://github.com/user-attachments/assets/1d6adf81-38b5-4b7c-974f-3115005b20ba" />


The optimal setting for Anodize Time is 40 minutes, 
which is the high level of this factor.

**Q5. What is the predicted L* and is it close 
to the target?**

The predicted L* at the optimal settings is 9.49. 
This is slightly below the target of 10 but falls 
within the acceptable range of 8 to 12.

**Q6. What is the predicted defect rate from 
the simulation?**

<img width="1152" height="729" alt="65_simulation_1" src="https://github.com/user-attachments/assets/cce71358-4d6d-43c6-b575-4198174d7fca" />

With the default standard deviation for Anodize Temp 
of 1.542 and 10,000 simulation runs, the predicted 
defect rate is approximately 0.77%.

**Q7. How does tighter temperature control affect 
the defect rate?**

<img width="1152" height="729" alt="65_simulation_2" src="https://github.com/user-attachments/assets/f9dfaf50-aa78-48bb-89c0-35d27b49092b" />


After reducing the standard deviation for Anodize 
Temp from 1.542 to 0.75 and increasing the 
simulation to 100,000 runs, the predicted defect 
rate dropped to approximately 0.1%. This represents 
an 87% reduction in defects achieved simply by 
improving temperature control consistency.

## Key Takeaways

This case study demonstrates the value of combining 
DOE with process simulation. The Prediction Profiler 
with desirability functions makes it possible to 
optimize multiple responses simultaneously, even 
when their individual goals may be in tension with 
one another. The simulation capability in JMP allows 
you to assess how process variation affects product 
quality before making changes on the production floor, 
providing a powerful tool for risk assessment and 
process improvement planning.
