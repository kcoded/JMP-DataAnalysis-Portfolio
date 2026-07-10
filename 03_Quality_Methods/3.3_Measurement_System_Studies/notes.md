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
| <img width="620" height="400" alt="03_measurement_system_process_map" src="https://github.com/user-attachments/assets/fd9406d3-05dd-4819-8709-dd04993ef5fa" /> | Input, process, and output map for a measurement system |
| <img width="787" height="317" alt="03_measurement_variation_cause_effect" src="https://github.com/user-attachments/assets/95214eec-be70-44d7-adc0-f6545b278e49" /> | Cause and effect diagram for sources of measurement variation |
| <img width="532" height="437" alt="03_gauge_study_design_setup" src="https://github.com/user-attachments/assets/ba79b174-78fb-409e-9edf-be5cd2dfa072" /> | Gauge study design setup for a two instrument, three inspector, ten part study |
| <img width="988" height="727" alt="03_gauge_study_worksheet" src="https://github.com/user-attachments/assets/9f6e579c-ecd0-4e4e-a068-02b6982c0616" /> | Generated worksheet from the gauge study design |
| <img width="933" height="852" alt="03_area_msa_combined_data" src="https://github.com/user-attachments/assets/30e8cd18-3ffd-494a-b11a-9e6b674f9073" /> | Combined measurement data table from the area measurement exercise |
| <img width="1023" height="638" alt="03_area_msa_variability_chart" src="https://github.com/user-attachments/assets/d36e02af-3ea7-4be4-9ba0-79405caa5118" /> | Variability chart for the area measurement exercise |
| <img width="1021" height="637" alt="03_area_msa_group_means" src="https://github.com/user-attachments/assets/de6c30ce-eb03-4b4e-b05e-dac5a77a677f" /> | Variability chart with group means displayed, showing reproducibility differences |
| <img width="1020" height="640" alt="03_area_msa_connect_cell_means" src="https://github.com/user-attachments/assets/a17e0130-1518-4840-8d8c-f0b21a6f45d6" /> | Variability chart with connected cell means, showing an interaction pattern |
| <img width="1023" height="636" alt="03_area_msa_variability_by_inspector" src="https://github.com/user-attachments/assets/798dc05a-4a4b-4545-af1f-a08157a7c652" /> | Variability chart broken out by inspector, supporting the bias study |
| <img width="1107" height="928" alt="03_area_msa_variance_components" src="https://github.com/user-attachments/assets/d1567621-b077-447b-9d96-ce0c51deb8e6" /> | Variance components table for the area measurement exercise |
| <img width="632" height="682" alt="03_area_msa_bias_report" src="https://github.com/user-attachments/assets/59f8a002-4749-4e18-992c-180e28688c5e" /> | Measurement bias report, including overall bias and bias by standard value |
| <img width="987" height="832" alt="03_mfi_emp_average_stddev_charts" src="https://github.com/user-attachments/assets/08a043bf-2df5-4188-8462-6d97a05da237" /> | Average and standard deviation charts for the melt flow index measurement study |
| <img width="968" height="833" alt="03_mfi_emp_avg_range_charts" src="https://github.com/user-attachments/assets/49ccf18b-b412-4379-a124-a5c5698f988d" /> | Average and range charts for the melt flow index measurement study |
| <img width="563" height="688" alt="03_mfi_emp_parallelism_plots" src="https://github.com/user-attachments/assets/f32b7825-a25f-464d-aadc-8536cdcf6248" /> | Parallelism plots for technician and instrument against batch |
| <img width="503" height="436" alt="03_mfi_emp_variance_components_gaugerr" src="https://github.com/user-attachments/assets/af91e024-8213-4e26-b9f6-2b746c25fc50" /> | Variance components and evaluating the measurement process results for melt flow index |
