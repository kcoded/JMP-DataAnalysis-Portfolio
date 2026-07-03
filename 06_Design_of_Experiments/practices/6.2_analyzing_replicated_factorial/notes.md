# 6.2 Designing a Full Factorial Experiment

## Objective
Design a randomized 2³ full factorial experiment to study 
three factors affecting particle count in a metal 
cleaning process.

## Factors and Response

| Factor | Low | High | Units |
|--------|-----|------|-------|
| Bath Time | 10 | 20 | hours |
| % Solution | 5 | 15 | |
| Rinse Time | 1 | 5 | hours |

Response: Y (Particles per cm²)
Goal: Maximize

## JMP Design Setup
<img width="835" height="430" alt="62_design_setup" src="https://github.com/user-attachments/assets/307815e4-2f7b-493c-9971-cf0ed833bfab" />

The experiment was designed using the Full Factorial 
Design platform in JMP under DOE, Classical. Three 
continuous factors were entered with their respective 
low and high values. The design was replicated once 
and run order was randomized using random seed 1234.

## Design Table
<img width="457" height="320" alt="62_design_table" src="https://github.com/user-attachments/assets/f6a27bc0-273c-4165-82ec-6d3660eb9e7c" />


## Questions and Solutions

**Q1. How many treatments are in this design?**

There are 8 treatments. A 2³ full factorial design 
produces 2×2×2 = 8 unique treatment combinations. 
A treatment is a unique combination of factor levels.

**Q2. How many runs are in this design?**

There are 16 runs. Each of the 8 treatments was 
replicated once, doubling the total number of runs.

**Q3. Interpret the pattern for the first trial.**

The pattern for row 1 is ++−, which means:

| Factor | Symbol | Setting |
|--------|--------|---------|
| Bath Time | + (high) | 20 hours |
| % Solution | + (high) | 15 |
| Rinse Time | − (low) | 1 hour |

**Q4. Which row is a replicate of row 1?**

Row 16 is the replicate of row 1. It has the same 
factor settings: Bath Time = 20, % Solution = 15, 
Rinse Time = 1.

## Key Takeaways

In a replicated full factorial design, every treatment 
is run more than once. This replication provides an 
estimate of experimental error, which is essential for 
testing the statistical significance of factor effects. 
Randomization protects against the influence of 
uncontrolled variables by averaging their effects 
across all treatments.

The pattern notation uses + for the high level and − 
for the low level of each factor, read from left to 
right in the order the factors appear in the design.
