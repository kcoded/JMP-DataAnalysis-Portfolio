# Statistical Process Control

## Common Cause and Special Cause Variation

Every process carries some amount of natural variation. When that variation comes only from sources built into the process itself, it is called common cause variation, and a process showing only this kind of variation is considered stable, or in control, and its future behavior can be predicted with reasonable confidence. When variation comes from an outside disruption, such as an equipment failure or a one time event, it is called special cause variation, and it makes the process unstable and unpredictable. A third category, systematic variation, follows a recurring pattern tied to a known cause, such as a seasonal shift, and it is easy to mistake for a special cause if the underlying driver is not recognized. A one time weather event, for example, is a special cause rather than a systematic one, even though weather feels seasonal in nature.

## Control Charts

A control chart plots a statistic over time against a center line, representing the process average, and upper and lower control limits, typically set at three standard deviations from that center line. A point falling outside those limits is likely the result of a special cause. The individual and moving range chart is the simplest form of this chart, plotting each measurement in time order alongside the range between consecutive observations. The control limits on this chart are calculated using the average moving range rather than the overall spread of the data, since using the overall spread would allow a special cause to inflate the limits and hide itself from detection.

For grouped data, an average and range chart, or an average and standard deviation chart, plots subgroup means on one panel and subgroup variability on a second panel. A three way chart adds a third component that tracks the variation between subgroup averages over time, which becomes useful when the variation within a subgroup is small compared to the variation between subgroups.

## Rational Subgrouping

A rational subgroup is not a random sample. It is a subgroup selected so that it contains only common cause variation: observations drawn from a single process, from a locally stable stretch of production, in time order, and independent of one another. Selecting observations at random across an entire process would blend different time periods together and introduce special cause variation into what should be a pure estimate of common cause noise.

## Deming's Funnel Experiment and Tampering

Adjusting a stable, on target process in reaction to ordinary variation, a practice known as tampering, generally makes the process worse rather than better. Deming's funnel experiment illustrates this using four rules for repositioning a funnel above a target. Only the first rule, making no adjustment at all, keeps variation at its natural minimum. Each of the other three rules, however well intentioned, increases variation over time.

## The Eight Tests for Special Causes

Beyond a single point falling outside the control limits, a set of eight standard tests, often called the Western Electric or Nelson rules, look for specific patterns within zones spaced one standard deviation apart between the center line and the control limits. These tests catch signals a simple limit check would miss, including a shift in the process mean, a steady trend, or a cyclical or stratified pattern. Running more tests increases sensitivity to genuine special causes, but it also increases the chance of a false alarm, so there is a real tradeoff involved in how many tests to apply.

## Control Charts with Phases

Adding a phase variable to a control chart, such as a before and after change, or a shift or location grouping, recalculates the center line and control limits separately for each phase. This tool serves two different purposes that are worth keeping distinct. One is confirming whether a sequential improvement actually took hold and held over time. The other is exploring whether parallel categories, such as different shifts or different production sites, genuinely differ from one another. In the metal parts thickness example, a phased chart showed the process mean moving toward target and variability decreasing across the before, after, and sustained phases, confirming the improvement was real and lasting rather than a temporary shift. In the melt flow index example, phasing by shift and by production site showed averages sitting close together relative to the process's natural variability, meaning there was no meaningful difference across either grouping.

## Practice Problems Completed

Variable classification for control charting using the crisis team dataset, individual and moving range charts for three process characteristics with an emphasis on reading stability, trend onset, and clustering patterns, distribution checks paired with control charts to confirm the normality assumption behind the standard tests, average and range and average and standard deviation charts for thickness and diameter data with interpretation of specific test violations, rational subgrouping characteristics, three way chart component identification, and phased charts confirming both a sustained thickness improvement and the absence of meaningful differences across shift and site groupings for melt flow index.

## Saved Images

File names below match exactly what is saved in the repository. File systems require a consistent naming pattern, so these use underscores between words rather than spaces, following the same convention used across every file in this portfolio.

| File | Description |
|---|---|
| `03_xf_imr_chart.png` | Individual and moving range chart for the Xf variable |
| `03_viscosity_imr_chart.png` | Individual and moving range chart for viscosity |
| `03_ambienttemp_imr_chart.png` | Individual and moving range chart for ambient temperature |
| `03_mfi_imr_chart_phase.png` | Individual and moving range chart for melt flow index, phased view |
| `03_distribution_ci_sa_xf.png` | Distribution histograms and summary statistics for three process variables |
| `03_ci_normal_quantile.png` | Normal quantile plot for the CI variable |
| `03_sa_normal_quantile.png` | Normal quantile plot for the SA variable |
| `03_xf_normal_quantile.png` | Normal quantile plot for the Xf variable |
| `03_sa_imr_chart_tests.png` | Individual and moving range chart with special cause test flags for SA |
| `03_ci_imr_chart_tests.png` | Individual and moving range chart with special cause test flags for CI |
| `03_thickness_xbar_r_chart.png` | Average and range chart for part thickness |
| `03_thickness_xbar_s_chart.png` | Average and standard deviation chart for part thickness |
| `03_diameter_xbar_r_test1.png` | Average and range chart for diameter, flagging a Test 1 violation |
| `03_diameter_xbar_r_test5.png` | Average and range chart for diameter, flagging a Test 5 violation |
| `03_diameter_xbar_s_chart.png` | Average and standard deviation chart for diameter |
| `03_diameter_xbar_s_test1.png` | Average and standard deviation chart for diameter, confirming a Test 1 violation |
| `03_diameter_xbar_s_test5.png` | Average and standard deviation chart for diameter, confirming a Test 5 violation |
| `03_thickness_phased_xbar_r.png` | Phased average and range chart for thickness across before, after, and sustained periods |
| `03_fillweight_3way_chart.png` | Three way control chart for fill weight |
| `03_mfi_phased_by_shift.png` | Phased individual and moving range chart for melt flow index by shift |
| `03_mfi_phased_by_quarry.png` | Phased individual and moving range chart for melt flow index by production site |
