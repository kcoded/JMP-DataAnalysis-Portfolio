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
| <img width="1023" height="515" alt="03_xf_imr_chart" src="https://github.com/user-attachments/assets/51e01c98-e0b4-4ebd-80bd-716781b475c6" /> | Individual and moving range chart for the Xf variable |
| <img width="1022" height="502" alt="03_viscosity_imr_chart" src="https://github.com/user-attachments/assets/a93ec703-d5d7-41bd-b1f7-9e24c9fd1924" /> | Individual and moving range chart for viscosity |
| <img width="1012" height="500" alt="03_ambienttemp_imr_chart" src="https://github.com/user-attachments/assets/7ca89525-9d4a-4145-8d88-87b60d25dec7" /> | Individual and moving range chart for ambient temperature |
| <img width="988" height="497" alt="03_mfi_imr_chart_phase" src="https://github.com/user-attachments/assets/81086cfc-33fd-49e2-b18d-9ceb697447cd" /> | Individual and moving range chart for melt flow index, phased view |
| <img width="742" height="768" alt="03_distribution_ci_sa_xf" src="https://github.com/user-attachments/assets/47308bda-35d0-48c7-9b43-5ee38d860f39" /> | Distribution histograms and summary statistics for three process variables |
| <img width="823" height="513" alt="03_ci_normal_quantile" src="https://github.com/user-attachments/assets/24423079-65db-4ad8-8291-798fd08f6f53" /> | Normal quantile plot for the CI variable |
| <img width="842" height="520" alt="03_sa_normal_quantile" src="https://github.com/user-attachments/assets/2c660edd-fd6d-4eca-9c89-ed13827a5971" /> | Normal quantile plot for the SA variable |
| <img width="817" height="518" alt="03_xf_normal_quantile" src="https://github.com/user-attachments/assets/337836ac-774e-45d6-b14e-18f06d5c0643" /> | Normal quantile plot for the Xf variable |
| <img width="1012" height="498" alt="03_sa_imr_chart_tests" src="https://github.com/user-attachments/assets/b278cf33-975d-470c-8ebe-16f039dc4458" /> | Individual and moving range chart with special cause test flags for SA |
| <img width="1008" height="486" alt="03_ci_imr_chart_tests" src="https://github.com/user-attachments/assets/5ebf2bde-a9be-492b-bdba-bc8099db62f3" /> | Individual and moving range chart with special cause test flags for CI |
| <img width="790" height="415" alt="03_thickness_xbar_r_chart" src="https://github.com/user-attachments/assets/d7644ea9-eb6d-4ec9-970c-267ec4428b9f" /> | Average and range chart for part thickness |
| <img width="1062" height="537" alt="03_thickness_xbar_s_chart" src="https://github.com/user-attachments/assets/5925b78a-b0e2-49f6-9132-c01aaf81a3a5" /> | Average and standard deviation chart for part thickness |
| <img width="936" height="533" alt="03_diameter_xbar_r_test1" src="https://github.com/user-attachments/assets/b5c31f45-b248-4659-93a6-d438d47ce107" /> | Average and range chart for diameter, flagging a Test 1 violation |
| <img width="935" height="525" alt="03_diameter_xbar_r_test5" src="https://github.com/user-attachments/assets/97548c85-5152-4c2e-ad8c-47da90171db0" /> | Average and range chart for diameter, flagging a Test 5 violation |
| <img width="1061" height="535" alt="03_diameter_xbar_s_chart" src="https://github.com/user-attachments/assets/35c53bc6-3a1c-4052-b16b-b8568eaa973c" /> | Average and standard deviation chart for diameter |
| <img width="1056" height="530" alt="03_diameter_xbar_s_test1" src="https://github.com/user-attachments/assets/2cda4fef-c1ae-4b88-b131-d5242c848572" /> | Average and standard deviation chart for diameter, confirming a Test 1 violation |
| <img width="1056" height="528" alt="03_diameter_xbar_s_test5" src="https://github.com/user-attachments/assets/bb97cb1c-560c-4568-b233-4fb127571ecf" /> | Average and standard deviation chart for diameter, confirming a Test 5 violation |
| <img width="1032" height="537" alt="03_thickness_phased_xbar_r" src="https://github.com/user-attachments/assets/7f88c6f3-ac04-4f0f-91ff-f4c2ac3be312" /> | Phased average and range chart for thickness across before, after, and sustained periods |
| <img width="1068" height="528" alt="03_fillweight_3way_chart" src="https://github.com/user-attachments/assets/06ab378f-e8a2-43cd-bd1c-fae45c780cc6" /> | Three way control chart for fill weight |
| <img width="1048" height="533" alt="03_mfi_phased_by_shift" src="https://github.com/user-attachments/assets/34c46865-3e51-47dc-b0fb-4af9f6a3c0df" /> | Phased individual and moving range chart for melt flow index by shift |
| <img width="1077" height="536" alt="03_mfi_phased_by_quarry" src="https://github.com/user-attachments/assets/58a18904-c393-4104-bd4d-7f73a10e8438" /> | Phased individual and moving range chart for melt flow index by production site |
