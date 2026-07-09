# Quality Methods
### Module 3: JMP Visual Six Sigma Certification

![JMP](https://img.shields.io/badge/Tool-JMP%2017%20Pro-blue)
![Method](https://img.shields.io/badge/Method-Quality%20Methods-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Badge](https://img.shields.io/badge/Credential-Credly%20Verified-blue)

---

## Overview

Quality Methods covers the statistical tools used to understand, control, and improve a process once data is being collected from it. This module is built around three connected questions. Is the process behaving consistently over time? Is it capable of meeting customer specifications? And can the measurement system being used to answer those first two questions actually be trusted?

This module covers statistical process control, process capability analysis, and measurement systems analysis in JMP. The practices completed here reflect real process and quality scenarios commonly found in manufacturing and process engineering environments, using datasets on metal part thickness and diameter, polymer temperature and melt flow index, part flatness, and a hands on measurement study I conducted myself.

---

## What I Learned

**Statistical Process Control**
A process shows either common cause variation, which is random and inherent to the process, or special cause variation, which comes from outside the process and makes it unpredictable. Control charts separate these two sources using a time ordered plot with a center line and upper and lower control limits. Individual and moving range charts, X-bar and R charts, X-bar and S charts, and three way charts each serve this purpose for different types of data. Rational subgrouping, the eight tests for special causes, and phased control charts all sharpen a chart's ability to detect real process changes without reacting to normal variation, which Deming's funnel experiment demonstrates can make a stable process worse rather than better.

**Process Capability**
Process capability compares the spread of a stable process to its customer specification limits using the Cp, Cpl, Cpu, and Cpk indices. Cp measures potential capability based on spread alone, while Cpk accounts for both spread and how well centered the process is, making the gap between the two a useful diagnostic for deciding whether to fix variability or centering first. Short term capability indices and long term performance indices reveal whether a process is stable over time, and capability analysis on nonnormal data requires fitting the correct distribution rather than assuming a normal curve, since using the wrong assumption can misstate the true defect rate by a wide margin.

**Measurement Systems Analysis**
Before trusting any conclusion drawn from process data, it is worth confirming the measurement system itself is accurate and precise. A measurement systems analysis examines five characteristics: repeatability, reproducibility, stability, bias, and linearity. Crossed study designs, variability charts, average and range charts, parallelism plots, variance components, and the Evaluating the Measurement Process method all help separate genuine part to part differences from noise introduced by the operators, gauges, or measurement procedure itself.

---

## Practice Problems

### 3.1 Statistical Process Control

Practice work in this section used the CrisisTeamData, MetalPartsAll, and Diameter SPC datasets to build and interpret individual and moving range charts, X-bar and R charts, X-bar and S charts, and a three way chart, along with phased control charts comparing process performance before and after an improvement.

Key questions addressed:
1. Which variables in the dataset are continuous, categorical, or identifiers, and how does that affect chart selection?
2. Which process characteristic is most stable, and what patterns appear in the less stable characteristics?
3. Which of the eight tests for special causes are violated, and what does each violation signal about the process?
4. Does a phased control chart show that a process improvement was sustained over time?

### 3.2 Process Capability

Practice work in this section used the MetalPartsAll, MetalPartsAfter, Impurity, and PartFlatness datasets to calculate and interpret capability indices under a range of conditions, including a before and after comparison and a dataset with a confirmed nonnormal distribution.

Key questions addressed:
1. What are the Cp, Cpl, Cpu, and Cpk values for a given process, and what do they reveal about centering and spread?
2. How do short term capability indices compare to long term performance indices, and what does a gap between them indicate about stability?
3. Has a process improvement effort reduced variability, improved centering, or both?
4. How does fitting the correct distribution change the estimated nonconformance rate for a nonnormal characteristic, compared to assuming normality?

### 3.3 Measurement Systems Analysis

Practice work in this section included designing a gauge study worksheet, conducting a hands on area measurement exercise with several other participants, and analyzing a destructive test measurement system using the Evaluating the Measurement Process method.

Key questions addressed:
1. How many measurements does a fully crossed gauge study design require per part, per inspector, and per repeat?
2. What do a variability chart, an average and range chart, and a parallelism plot each reveal about repeatability, reproducibility, and interactions?
3. How much of the total measurement variance comes from the parts themselves versus the measurement system, and is the system capable of distinguishing good product from bad?
4. Is there a statistically significant bias in the measurement system, and does that bias change across the range of values measured?

---

## Tools and Software

JMP 17 Pro was used for all analysis and visualization in this module. Specific platforms used include the Control Chart Builder, the Distribution platform with Continuous Fit, the Process Capability platform, the Gauge Study Design platform under Design of Experiments, and the Measurement Systems Analysis platform under Quality and Process.

---

## Data Sources

All datasets were provided as part of the JMP Visual Six Sigma online statistics course, with the exception of the Area MSA exercise data, which I collected myself alongside other course participants. The files used in this module include CrisisTeamData.jmp, MetalPartsAll.jmp, MetalPartsAfter.jmp, Diameter SPC.jmp, Impurity.jmp, PartFlatness.jmp, MSA_MFI_Initial.jmp, and Area MSA Exercise Combined.jmp.

---

## Course Attribution

This work was completed as part of the JMP Visual Six Sigma online statistics course offered by JMP Learn.

Course: [JMP Visual Six Sigma](https://www.jmp.com/en/online-statistics-course)

All analyses were performed independently using course data and JMP software. Findings and interpretations are my own.

---

## Certification

Upon completing this module, a verified digital credential was issued through Credly.

[View Quality Methods Badge](https://www.credly.com/earner/earned/share/69bbf8d0-888d-41b8-bada-d4e10623d9b9)
