# Design of Experiments (DOE)
### Module 6: JMP Visual Six Sigma Certification

![JMP](https://img.shields.io/badge/Tool-JMP%2017%20Pro-blue) 
![Method](https://img.shields.io/badge/Method-Design%20of%20Experiments-orange) 
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Badge](https://img.shields.io/badge/Credential-Credly%20Verified-blue)

---

## Overview

Design of Experiments (DOE) is a structured and efficient approach to collecting data and making discoveries. Rather than changing one factor at a time or relying on trial and error, DOE allows you to study multiple factors simultaneously, understand how they interact, and identify the settings that produce the best outcome.

This module covers the full DOE workflow, from designing experiments in JMP to analyzing results and making data-driven recommendations. The practices completed here reflect real experimental scenarios commonly found in manufacturing and process engineering environments.

---

## What I Learned

**Factorial Experiments**
Full factorial designs allow you to test every possible combination of factor levels. This makes it possible to estimate main effects, two-way interactions, and higher-order interactions with full confidence. Replicating treatments provides an estimate of experimental error, which is essential for statistical testing.

**Screening Experiments**
When the number of factors is large, running a full factorial becomes impractical. Fractional factorial designs and custom screening designs allow you to study many factors efficiently by running only a subset of the total treatments. The trade-off is that some effects become aliased, meaning they cannot be estimated independently.

**Response Surface Experiments**
Once the important factors have been identified, response surface designs are used to find the optimal operating conditions. Central Composite Designs (CCD) add axial points to a factorial design, enabling the estimation of quadratic effects and the modeling of curvature in the response surface.

**DOE Guidelines**
Good experimental design requires careful planning. The ten-step DOE guideline framework covers everything from defining the problem and identifying responses to preparing the logistics of running the experiment and drawing conclusions. A well-planned experiment reduces the risk of wasted resources, invalid results, and missed effects.

---

## Practice Problems

### 6.1 Designing a Full Factorial Experiment
A 2³ full factorial design was created in JMP to study three factors: Bath Time, Percentage Solution, and Rinse Time. The design was replicated once, resulting in 16 total runs. Run order was randomized to control for lurking variables.

Key questions addressed:
1. How many treatments are in this design?
2. How many runs are in this design?
3. What does the pattern for the first trial represent?
4. Which row is a replicate of row 1?

### 6.2 Analyzing a Replicated Full Factorial Experiment
The Particles 2 dataset was used to analyze a replicated full factorial experiment with four factors: Bath Time, Percentage Solution, Rinse Time, and Type. The response was Particles per cm². Nonsignificant terms were removed one at a time using backward elimination. The Prediction Profiler was used to identify optimal factor settings that minimize particle count.

Key questions addressed:
1. How many main effects and two-way interactions are in the model?
2. Which three effects are most significant?
3. What terms remain in the reduced model?
4. What factor settings minimize Particles, and what is the predicted response?

### 6.3 Designing a Fractional Factorial Experiment
A screening experiment was designed for five continuous factors using the JMP Screening platform. A 2⁵⁻¹ fractional factorial design with four center points was selected, resulting in 20 total runs. The aliasing structure was reviewed to confirm that main effects and two-way interactions could be estimated independently.

Key questions addressed:
1. What are the candidate screening designs for this scenario?
2. Which effects are aliased in the selected design?
3. How many runs are in the final design including center points?
4. What do the center points represent?

### 6.3 Analyzing a 20-Run Custom Design (Reactor 20)
The Reactor 20 Custom dataset was used to analyze a 20-run optimal custom design with five factors and one response: Percent Reacted. The model was reduced by removing nonsignificant terms. The Prediction Profiler and desirability function were used to identify the factor settings that maximize reactor output.

Key questions addressed:
1. Which terms are significant at the 0.05 level?
2. How many terms are in the reduced model?
3. What factor settings maximize Percent Reacted?
4. What does the 95% confidence interval for the predicted response represent?

### 6.4 Analyzing a Custom Central Composite Design (CCD)
The Custom CCD 3 Factors dataset was used to fit a full second-order polynomial model for Yield based on three variables: Catalyst, Temperature, and Time. The model included main effects, two-way interactions, and quadratic terms. Lack of fit was assessed and the Prediction Profiler was used to identify optimal conditions.

Key questions addressed:
1. Is there evidence of lack of fit?
2. Which three effects are most significant?
3. What are the optimal factor settings to maximize Yield?
4. What does the Response Surface solution suggest?

### 6.4 Analyzing a Custom Response Surface Design (5 Factors)
The Custom 5 Response Surface dataset was used to analyze a 22-run response surface experiment with five factors and one response: Yield. The model was reduced by removing nonsignificant terms. Diagnostic plots were used to validate the model, and the Prediction Profiler was used to identify the optimal settings.

Key questions addressed:
1. Which terms are in the reduced model?
2. Do the diagnostic plots reveal any unusual patterns or outliers?
3. What are the optimal factor settings, and what is the predicted Yield?

### 6.5 Anodize Case Study
The Anodize dataset was used to analyze a multi-response experiment with four responses: Thickness, L*, a*, and b*. Reduced models were fit for each response. The Prediction Profiler was used with desirability functions to identify factor settings that simultaneously satisfy all response goals. A simulation was run to estimate the predicted defect rate under different levels of process variation.

Key questions addressed:
1. Which effects are in the reduced model for a*?
2. What are the starting values and predicted responses in the Profiler?
3. What is the response goal, target, and acceptable limits for L*?
4. What is the optimal setting for Anodize Time?
5. What is the predicted defect rate, and how does tighter temperature control affect it?

---

## Tools and Software

JMP 17 Pro was used for all experimental design, analysis, and visualization in this module. Specific platforms used include the Full Factorial Design platform, the Screening Design platform, the Custom Designer, Fit Model with the Response Surface macro, the Prediction Profiler, and the Simulator.

---

## Data Sources

All datasets were provided as part of the JMP Visual Six Sigma online statistics course. The files used in this module include Particles 2.jmp, Reactor 20 Custom.jmp, Custom CCD 3 Factors.jmp, Custom 5 Response Surface.jmp, and Anodize.jmp.

---

## Course Attribution

This work was completed as part of the JMP Visual Six Sigma online statistics course offered by JMP Learn.

Course: [JMP Visual Six Sigma](https://www.jmp.com/en/online-statistics-course)

All analyses were performed independently using course data and JMP software. Findings and interpretations are my own.

---

## Certification

Upon completing this module, a verified digital credential was issued through Credly.

[View DOE Badge](https://www.credly.com/badges/a97fc9cb-7f6d-4bb8-b4b7-8096b859c840/public_url)
