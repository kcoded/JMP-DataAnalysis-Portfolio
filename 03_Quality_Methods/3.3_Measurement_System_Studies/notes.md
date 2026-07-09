# Measurement Systems Analysis

## Purpose of a Measurement Systems Analysis

The total variability observed in any measurement is the sum of the actual part to part variability and the measurement system's own error. A measurement systems analysis has two goals: determining whether the measurement system measures accurately, without bias, and determining whether it is precise enough to detect real differences between parts. Before trusting any conclusion drawn from process data, including control charts and capability indices, it is worth confirming the measurement system itself is trustworthy.

## The Five Characteristics

Repeatability is the variation in repeated measurements taken by the same operator, with the same gauge, on the same part, under the same conditions, effectively the measurement system's own baseline noise. Reproducibility is the variation between different operators measuring the same part with the same gauge. Together these two form the repeatability and reproducibility study commonly referred to as a gauge study.

Stability is whether the measurement system's average and standard deviation remain consistent over time. Bias is the difference between the average of measured values and the true, or standard, value, representing a systematic offset separate from variability. Linearity is whether that bias stays constant across the full operating range of the gauge, rather than growing or shrinking at different points along that range.

An ideal measurement system is stable, accurate, and precise relative to the specification limits it will be used against.

## Designing a Crossed Measurement Study

In a crossed measurement study, every inspector measures every part with every gauge involved. Parts should be presented to operators in random order, both to avoid time related effects such as fatigue or learning, and to prevent an operator from remembering a previous measurement of the same part and anchoring to it, which would artificially inflate apparent repeatability. In a fully crossed design, the number of measurements attributable to any single factor, whether per part, per inspector, or per repeat, is the grand total divided by that factor's own number of levels. It is easy to accidentally report the number of levels of a factor rather than the actual measurement count, so this distinction is worth checking carefully.

## Visualizing a Measurement Study

A variability chart plots every combination of part, inspector, and gauge, and serves as the first tool for exploring repeatability, visible as the vertical spread within a single part and inspector combination, reproducibility, visible as differences between each inspector's average, and interactions, visible as differences in the pattern of measurements across parts for different inspectors.

Average and range control charts are interpreted differently in this context than in standard process control. For a capable measurement system, most points on the average chart should actually fall outside the control limits. Those limits are calculated from measurement error alone, so if genuine part to part differences are large enough to push most averages outside such tight limits, the measurement system can reliably tell parts apart. If most points fall inside the limits instead, the measurement system's own noise is too large relative to the real differences it is meant to detect.

A parallelism plot checks for interactions directly. If the lines representing each inspector or instrument move together across parts or batches, they are parallel, and there is no interaction. If the lines cross or diverge, that divergence is itself the interaction, indicating that the effect of the part or batch depends on which inspector or instrument is doing the measuring.

## Variance Components and Gauge Repeatability and Reproducibility

A variance components analysis breaks total variation down into its sources and reports each as a percentage of the total. In a healthy measurement system, the part to part component should be by far the largest, since that represents real signal. If a measurement system component competes with or exceeds that real signal, the measurement noise is drowning out the differences the system is supposed to detect.

The Evaluating the Measurement Process method reports repeatability and reproducibility combined into a single measurement system variance figure. When calculating the total variance attributable to the measurement system specifically, only the repeatability, reproducibility, and any interaction terms involving the measurement system should be combined, while genuine product variation should be excluded, even though it appears in the same output table under a total variation heading. Comparing six times the measurement system's own standard deviation against the width of the specification limits provides a direct way to judge whether the measurement system is capable of distinguishing good product from bad. If the measurement system's own natural spread is wider than the tolerance itself, the gauge cannot reliably do its job.

## Studying Bias and Linearity

Bias is calculated as the measured value minus the standard, or true, value. A negative bias means measurements tend to run below the true value on average, while a positive bias means they run above it. Statistical significance testing on the average bias, using a t ratio, a probability value, and a confidence interval, indicates whether an observed offset is a genuine systematic effect or simply sampling noise. Breaking bias down across the range of true values studied is a direct linearity check. If bias stays roughly constant across all standards, the system is linear. If bias grows or shrinks systematically as the true value increases, that points to a linearity problem layered on top of any overall bias.

## Practice Problems Completed

A gauge study design worksheet for a two instrument, three inspector, ten part, two repeat crossed design, including correctly calculating the number of measurements per part, per inspector, and per repeat. Reasoning through the possible causes of an interaction between parts and inspectors, including part orientation and handling, rounding conventions, part specific features, batch preparation, and equipment setup differences. A variability chart analysis on a hands on area measurement exercise conducted with several other participants, identifying repeatability, reproducibility, and an interaction between parts and inspectors. An evaluation of the measurement process on a destructive test example involving melt flow index, including reading average and standard deviation charts correctly, identifying parallelism and interaction patterns for both technician and instrument, and correctly isolating the measurement system's own variance from total variance. A variance components analysis confirming that part to part variation was the dominant and desirable source of variation in the same area measurement exercise. A bias and linearity study on that exercise, finding a statistically significant underestimation bias along with a linearity problem where bias grew substantially worse for larger objects.

## Saved Images

File names below match exactly what is saved in the repository. File systems require a consistent naming pattern, so these use underscores between words rather than spaces, following the same convention used across every file in this portfolio.

| File | Description |
|---|---|
| `03_measurement_system_process_map.png` | Input, process, and output map for a measurement system |
| `03_measurement_variation_cause_effect.png` | Cause and effect diagram for sources of measurement variation |
| `03_gauge_study_design_setup.png` | Gauge study design setup for a two instrument, three inspector, ten part study |
| `03_gauge_study_worksheet.png` | Generated worksheet from the gauge study design |
| `03_area_msa_combined_data.png` | Combined measurement data table from the area measurement exercise |
| `03_area_msa_variability_chart.png` | Variability chart for the area measurement exercise |
| `03_area_msa_group_means.png` | Variability chart with group means displayed, showing reproducibility differences |
| `03_area_msa_connect_cell_means.png` | Variability chart with connected cell means, showing an interaction pattern |
| `03_area_msa_variability_by_inspector.png` | Variability chart broken out by inspector, supporting the bias study |
| `03_area_msa_variance_components.png` | Variance components table for the area measurement exercise |
| `03_area_msa_bias_report.png` | Measurement bias report, including overall bias and bias by standard value |
| `03_mfi_emp_average_stddev_charts.png` | Average and standard deviation charts for the melt flow index measurement study |
| `03_mfi_emp_avg_range_charts.png` | Average and range charts for the melt flow index measurement study |
| `03_mfi_emp_parallelism_plots.png` | Parallelism plots for technician and instrument against batch |
| `03_mfi_emp_variance_components_gaugerr.png` | Variance components and evaluating the measurement process results for melt flow index |
