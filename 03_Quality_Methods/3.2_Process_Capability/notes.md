# Process Capability

## Control Limits Versus Specification Limits

These two concepts are easy to blend together but come from entirely different places. Control limits are calculated from the process data itself, based on observed variability, and describe what the process is actually doing. Specification limits, sometimes called tolerance, are defined by the customer and describe what is acceptable. A process can be perfectly in control while still producing output outside its specification, and capability analysis exists to measure that gap.

## The Process Capability Study Sequence

A capability index calculated on an unstable process cannot be trusted, since the underlying formulas assume the variation being measured is stable, common cause variation. The correct sequence is to determine whether the process is stable, bring it to stability if it is not, and only then compute a capability index.

## Cp, Cpl, Cpu, and Cpk

The Cp index compares the width of the specification limits to the width of the process spread, without any regard for where the process is centered. This is why Cp is also called the potential process capability, since it answers the question of whether the process could fit within specification if it were perfectly centered.

Cpl and Cpu bring the process mean back into the calculation, measuring capability relative to the lower and upper specification limits individually. Cpk is the smaller of these two values, since a process is only as capable as its nearest, most at risk limit. When a process is perfectly centered, Cpl and Cpu are equal, so Cp and Cpk match. When the mean drifts off center, Cpk drops below Cp, and if the mean drifts past a specification limit entirely, Cpk becomes negative.

The size of the gap between Cp and Cpk is itself a useful diagnostic. A small gap means the process is well centered and the remaining question is whether the spread itself, reflected in the Cp value, is good enough. A large gap points to centering as the more urgent and often cheaper problem to fix compared to reducing variability.

Common industry benchmarks treat a Cpk below one as not capable, a Cpk of exactly one as marginally capable, a Cpk of 1.33 as the most widely cited minimum acceptable threshold, and 1.67 or higher as good to excellent depending on the industry.

## Short Term Versus Long Term Capability

Cp and Cpk use a short term, within subgroup estimate of standard deviation, representing common cause variation alone. Pp and Ppk use a long term, overall estimate calculated across the entire dataset, representing common cause and special cause variation together. If the long term estimate comes out meaningfully lower than the short term estimate, that gap is a direct signal the process is unstable, since something is happening between subgroups that a within subgroup view alone would not reveal. The ratio of overall variability to within subgroup variability is formalized as the stability index, which should sit close to one for a genuinely stable process.

## Sample Size and Estimate Precision

Capability indices are estimates of an unknown true value, and like any statistical estimate, they carry sampling variability that is especially pronounced with small sample sizes. More subgroups produce a more precise and trustworthy estimate. This is a separate concern from whether the subgroups were properly constructed as rational subgroups in the first place, since one is a precision problem solved with more data, and the other is a validity problem solved through proper study design.

## Capability Analysis for Nonnormal Data

The standard capability formulas assume the underlying distribution is approximately normal. When a distribution is confirmed nonnormal through a histogram, a comparison of mean and median, and a normal quantile plot, the correct approach is to fit the best matching distribution and calculate capability from that distribution's own percentiles rather than from the sample mean and standard deviation directly.

This distinction matters more than it might first appear. In the part flatness example, running the standard normal theory calculation on confirmed nonnormal, right skewed data produced a Ppk of 1.394 and an estimated nonconformance rate of 0.0015 percent. Running the correct calculation, based on a fitted Weibull distribution, on the same data produced a Ppk of 0.821 and an estimated nonconformance rate of 0.4588 percent, a difference of roughly three hundred times in the estimated defect rate, and the difference between a process that looks comfortably capable and one that clearly is not. Both the incorrect and corrected analyses are preserved in this repository as an intentional learning artifact, since the contrast itself is one of the more valuable lessons from this section.

## Synthesis: Stability and Capability Together

A process can be stable and capable, which is the goal, stable but not capable, meaning it is consistent but does not fit specification, capable but not stable, meaning it fits specification today but could drift out at any time, or neither. Poor performance can be diagnosed by working through three questions in order: is the process unstable, in which case the priority is improving stability and removing special causes, is it off target, in which case the priority is working on centering, or is it simply too variable, in which case the priority is reducing common cause variation.

## Practice Problems Completed

A full capability study on thickness data, including a manual calculation confirmed against software output, within versus overall sigma, the stability index, and the nonconformance rate. A full capability study on temperature data from an impurity dataset, including a stability check, a normality check, a performance index calculation, an on target assessment, and the total nonconformance rate. A before and after capability comparison on thickness data, separating the contribution of reduced variability from improved centering. A nonnormal capability analysis on part flatness data, including the distribution fit and the corrected versus incorrect capability comparison described above.

## Saved Images

File names below match exactly what is saved in the repository. File systems require a consistent naming pattern, so these use underscores between words rather than spaces, following the same convention used across every file in this portfolio.

| File | Description |
|---|---|
| `03_thickness_distribution_capability.png` | Distribution and summary statistics for thickness prior to capability analysis |
| `03_thickness_imr_chart_capability.png` | Individual and moving range chart confirming stability for thickness |
| `03_thickness_capability_report.png` | Full capability report for thickness, confirming manual calculations |
| `03_temp_imr_chart.png` | Individual and moving range chart for temperature |
| `03_temp_normal_quantile.png` | Normal quantile plot confirming approximate normality for temperature |
| `03_temp_capability_report.png` | Full capability report for temperature, including performance indices and nonconformance rate |
| `03_thickness_xbar_r_before.png` | Average and range chart for thickness before the process improvement |
| `03_thickness_xbar_r_after.png` | Average and range chart for thickness after the process improvement |
| `03_thickness_capability_before.png` | Capability report for thickness before the process improvement |
| `03_thickness_capability_after.png` | Capability report for thickness after the process improvement |
| `03_partflatness_distribution.png` | Distribution and summary statistics for part flatness, showing a right skewed pattern |
| `03_partflatness_weibull_fit.png` | Distribution fit comparison identifying the Weibull distribution as the best fit |
| `03_partflatness_capability_normal_incorrect.png` | Capability report calculated incorrectly using normal theory on nonnormal data, preserved as a learning artifact |
| `03_partflatness_weibull_capability.png` | Corrected capability report calculated using the fitted Weibull distribution |
| `03_partflatness_normal_vs_weibull_note.md` | Written explanation comparing the incorrect and corrected capability approaches |
| `03_poor_performance_decision_tree.png` | Decision tree for diagnosing poor process performance across stability, centering, and variability |
