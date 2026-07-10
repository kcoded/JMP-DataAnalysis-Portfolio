# Quality Methods: Quiz Reference Guide
### Module 3: JMP Visual Six Sigma Certification

This document collects every quiz question worked through during this Module, along with the right approach for each one. It is meant as a standing reference to review the reasoning behind these concepts without needing to revisit the full course material.

---

## 3.1 Statistical Process Control

**Question: How are the control limits for an individuals chart calculated?**
Answer: Using the moving range between consecutive points to estimate the standard deviation.
Explanation: It might seem natural to calculate the overall standard deviation of every individual data point, but that is not how an individuals chart works. The chart instead uses the average moving range between consecutive points to estimate variation. This matters because if a special cause is present somewhere in the data, the overall standard deviation gets inflated by that special cause, which would widen the control limits and could mask the very signal you are trying to detect. Using the moving range instead keeps the estimate based on short term, point to point variation, making it more resistant to that kind of distortion.

**Question: Matching Deming's four rules for the funnel experiment to real world examples.**
Answer: Rule One, no adjustment, matches monitoring a process with control charts and reacting only when a special cause occurs. Rule Two, exact compensation, matches adjusting a setting to zero based on the result of the last production run. Rule Three, overcompensation, matches adjusting production schedules based on the most recent prices and inventory levels. Rule Four, consistency, matches a new operator learning a task directly from the current operator.
Explanation: Deming's funnel experiment shows that only leaving a stable process alone, Rule One, keeps variation at its natural minimum. The other three rules all represent well intentioned attempts to correct the process that end up increasing variation instead. Zeroing out based on the last result, overcorrecting based on the latest fluctuation, and passing along whatever the previous person was doing are all examples of tampering with a process that would have been better left alone.

**Question: What is the value of the eight tests for special causes to a problem solving team?**
Answer: All of the listed benefits apply. The tests help identify when something has changed in the process, help identify trends, help identify cycles or patterns, help identify when something has gone wrong, and help identify when the process mean has shifted.
Explanation: Each of the eight tests is designed to catch a different signature of change in a process. Together they give a much richer diagnostic toolkit than simply checking whether a single point falls outside the control limits, since they point toward what kind of special cause to look for, whether that is a sudden jump, a gradual drift, an alternating pattern between two sources, or a subtler issue like mixed populations hiding inside one subgroup.

**Question: What does it mean when Test 5 is violated, showing two out of three points in a row beyond two standard deviations from the mean?**
Answer: This indicates a possible shift in the process mean.
Explanation: Test 5 flags a positive result when two out of three consecutive points fall beyond two standard deviations on the same side of the center line, with the third point also required to be at or beyond that same boundary. This pattern is unlikely to occur under normal common cause variation alone, so it signals that the average level of the process itself may have moved.

**Question: Which of the following are characteristics of a rational subgroup?**
Answer: The observations are from a single process, the observations are from a stable process, the observations are time ordered, and the observations are independent from one another. Randomly selecting observations from across the process is not a characteristic of a rational subgroup.
Explanation: A rational subgroup is deliberately not a random sample. The goal is to select observations so that each subgroup captures only common cause variation, which means drawing from a single, locally stable stretch of production, in time order, with independent values. Randomly sampling across a longer stretch of time would risk mixing different production periods together and contaminating the subgroup with special cause variation, which defeats the purpose of the chart.

**Question: What is plotted on a three way control chart?**
Answer: All three elements are plotted: within subgroup variation, between subgroup variation, and subgroup means.
Explanation: A standard average and range chart only separates variation into within subgroup variation and how much the subgroup averages bounce around the overall average. A three way chart adds a third view, tracking how much the subgroup averages themselves are drifting from one subgroup to the next as their own separate time series. This becomes especially useful when there is reason to suspect meaningful movement happening at a slower timescale than a single average and range chart would reveal on its own.

**Question: Matching terms to the correct definition, distinguishing control limits from specification limits.**
Answer: Specification limits are used to determine whether a product is good or bad, are defined by the customer, and define a range of acceptable values. Control limits are calculated from data, can be based on subgroup means, and are calculated based on observed variability.
Explanation: These two concepts are often blended together but come from entirely different sources. Specification limits come from outside the process, reflecting what the customer considers acceptable, sometimes referred to as the tolerance. Control limits come from the process data itself and describe what the process is actually doing. A process can be perfectly in control while still producing output that falls outside specification, which is exactly the gap that capability analysis is built to measure.

---

## 3.2 Process Capability

**Question: How should the following Cp and Cpk value pairs be interpreted in terms of process centering and spread? Cp of 0.8 with Cpk of 0.5, Cp of 1.5 with Cpk of 1.5, and Cp of 1.0 with Cpk of negative 0.5.**
Answer: A Cp of 0.8 with a Cpk of 0.5 describes a process that is off target and whose spread is wider than the specification width. A Cp of 1.5 with a Cpk of 1.5 describes a process that is on target with a spread narrower than the specification width. A Cp of 1.0 with a Cpk of negative 0.5 describes a process whose mean has moved entirely outside the specification limits, even though the spread itself matches the specification width.
Explanation: Cp only measures whether the spread of the process could fit within specification, assuming perfect centering, while Cpk measures both spread and actual centering together. When Cp and Cpk are equal, the process is centered, and the value itself tells you whether the spread is comfortable or not. When there is a gap between the two, that gap tells you the process is off target. A negative Cpk specifically means the process mean has drifted past a specification limit entirely, which is a much more serious signal than simply being off center.

**Question: Given a stable process with Cp of 1.4 and Cpk of 0.5, which improvement should be prioritized first?**
Answer: Shifting the process to target.
Explanation: The large gap between Cp and Cpk is the key piece of evidence here. Since Cp only measures spread and Cpk measures spread together with centering, a healthy Cp alongside a much lower Cpk means the spread itself is not the problem. The process is simply aimed at the wrong place. Re-centering the process is usually a faster and less expensive fix than reducing variability, and it would bring Cpk back up toward the already acceptable Cp value.

**Question: A capability study shows a short term Cp of 1.5 and a long term Cp, or Pp, of 0.9. How should this be interpreted?**
Answer: The process is unstable, meaning special cause variation is present.
Explanation: Short term capability is based on within subgroup variation, which should reflect common cause variation only if the subgroups were properly formed. Long term capability is based on the overall variation across the entire dataset. If the long term estimate comes out meaningfully lower than the short term estimate, that gap means the overall spread across the full dataset is wider than what shows up within any single subgroup, and that extra spread has to be coming from somewhere between the subgroups. This is the same kind of signal a control chart's special cause tests are designed to catch, just expressed through the capability numbers instead.

**Question: With twenty five subgroups already available in an example dataset, which sample size would provide a more precise estimate of process capability?**
Answer: Using data from fifty to one hundred subgroups.
Explanation: Capability indices are point estimates of an unknown true value, and like any statistical estimate, they carry sampling variability that shrinks as the sample size grows. A capability index calculated from only a handful of subgroups could bounce around considerably just due to random sampling, while a much larger sample stabilizes the estimate and reflects the true underlying process more accurately. This is separate from whether the subgroups were properly constructed as rational subgroups in the first place, since inadequate subgrouping is a validity problem, not simply a sample size problem.

---

## 3.3 Measurement Systems Analysis

**Question: Matching terms to their correct definitions: stability, reproducibility, repeatability, and bias.**
Answer: Stability is having the same mean and standard deviation when taking measurements on the same part over time. Reproducibility is having low measurement error across different operators measuring the same parts. Repeatability is having low measurement error associated with multiple measurements taken under identical conditions. Bias is when, on average, the measurement system overstates or understates the true value.
Explanation: These four terms describe different characteristics of a measurement system and are easy to mix up, particularly reproducibility and repeatability. Repeatability holds the operator constant and asks how much results vary when the same person measures the same part again. Reproducibility holds the part constant and asks how much results vary across different people. Stability is about consistency over time rather than across people, and bias is about systematic offset from the truth rather than about variability at all.

**Question: In a crossed measurement systems analysis, should parts be presented to operators in random order? True or false.**
Answer: True.
Explanation: Presenting parts in a fixed, predictable order risks introducing time related effects, such as an operator improving or fatiguing partway through the sequence, and it also risks the operator remembering a previous measurement of the same part and anchoring their new estimate to it. Both effects would distort the study, making the measurement system appear more or less consistent than it actually is. Randomizing the order removes both risks and ensures each measurement reflects a genuinely independent judgment.

**Question: An average bias of negative 0.37 was calculated for a measurement system. What does this mean?**
Answer: On average, the measurements are below the true value.
Explanation: Bias is calculated as the measured value minus the true, or standard, value, so a negative number means measurements are running low relative to the truth on average. It is important to note this describes the average tendency of the system rather than every individual measurement, since some individual readings could still fall above the true value while still being outweighed by enough low readings to pull the average into negative territory.

---

## A Few Threads That Ran Through the Whole Module

Several ideas came up repeatedly across these questions and are worth holding onto as general principles rather than isolated facts.

Stability always needs to be confirmed before capability is trusted. A capability number calculated on an unstable process does not tell you anything reliable about future performance.

The size of a gap between two related numbers is often more informative than either number alone. This shows up in the gap between Cp and Cpk, which reveals a centering problem, and in the gap between short term and long term capability, which reveals an instability problem.

Repeatability, reproducibility, bias, and stability describe genuinely different things, even though they can sound similar. Getting the distinctions right matters because each one points toward a different kind of fix.

Randomization protects the integrity of a study in more than one way at once, whether that is preventing lurking variables in a designed experiment or preventing memory and fatigue effects in a measurement study.
