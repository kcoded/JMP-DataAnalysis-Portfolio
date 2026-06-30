# 📊 Data Quality, Variable Coding & Data Preparation in JMP

## The Core Question
Before running any analysis, how do you know your data is ready? This project answers that question by walking through a complete data preparation workflow, finding problems, fixing them, restructuring the data, and building calculated columns all using JMP Pro.

---

## Why This Matters
Imagine making a business decision based on a chart that looks clean but was built on data where half the values were missing, numbers were stored as text, or the same location was spelled three different ways. The chart would look fine. The decision would be wrong.

This module is about catching those problems before they reach the analysis stage and connecting each fix to what it means in a real manufacturing environment.

---

## Badge Earned
**Exploratory Data Analysis**
Issued by: SAS
[View Credly Badge](https://www.credly.com/go/G8NgTnzNjSfbWz2kwfq8HQ)

---

## Tools Used
- JMP 17 Pro: Columns Viewer, Distribution Platform, Missing Data Pattern, Treemap, Recode, Formula Editor, Stack, Concatenate, Join

---

## Part 1: Spotting Data Problems

There are four types of data quality issues. Each one is different, and each one requires a different fix.

| Problem Type | What It Means | Real Example Found |
|-------------|--------------|-------------------|
| **Incorrect Formatting** | A variable is stored as the wrong type | Lot numbers stored as continuous numbers instead of labels |
| **Missing Data** | Some rows have no value for a variable | The `acceptable?` column was blank in 8 rows |
| **Dirty Data** | The same thing is written in multiple ways | Canada entered as "Canada", "Can."; EU entered as "EU", "E.U.", "Europe" |
| **Incomplete Data** | A variable was never properly collected | `density` was 40 for every single row — no variation at all |

### Why Dirty Data Is Dangerous

If location is entered as "EU", "E.U.", and "Europe", JMP treats these as three completely separate categories. A bar chart that should show 3 bars will show 9. Every analysis grouping by location will be wrong not because the statistics are wrong, but because the categories are broken.

**Particle Size Example:**
Values: *Small, small, Medium, Med., medium, Medium, Small*
- There are only **2 real categories** Small and Medium
- But because of inconsistent spelling and capitalization, JMP sees **5 categories**
- A bar chart produces **5 bars instead of 2**

---

## Part 2: Coding Variables Correctly

Not every number in a dataset should be treated as a number you can calculate with. This is one of the most common mistakes in data preparation.

### The Simple Rule
> **If averaging it makes no sense, it should be coded as nominal.**

| Variable | Should You Average It? | Code It As |
|----------|----------------------|-----------|
| Lot number (D624310MQ0) | No:- it is just a label | Nominal |
| Chamber number (1, 2, 3) | No:- it identifies a location | Nominal |
| Yield % | Yes:- meaningful average | Continuous |
| Temperature | Yes:- meaningful average | Continuous |
| Processing status (Pass/Partial/Fail) | No:- but order matters | Ordinal |

### What Happens When You Get It Wrong

When `lot number` is coded as continuous, JMP calculates a mean lot number and a standard deviation; numbers that mean absolutely nothing. It looks like real output. It is not.

---

## Part 3: Semiconductor Connection: Slot IDs and Rework Decisions

In semiconductor manufacturing, each lot holds 25 wafers loaded into slots numbered 1 through 25. The slot number alone does not tell you much, but combined with processing status, it drives real decisions on the factory floor.

| Processing Status | What Happens Next | Business Impact |
|------------------|------------------|----------------|
| Fully processed | Move to test or ship | Generates revenue |
| Partially processed | Evaluate for rework | Recovers cost |
| Unprocessed | Re-split into a new lot | Returns to capacity planning |

**The coding connection:**
- Slot number → **Nominal** (it is a position label, not a measurement)
- Processing status → **Ordinal** (Unprocessed → Partial → Complete has a natural order)
- Yield % → **Continuous** (you average and track this over time)

If slot number is coded as continuous, JMP will try to average positions 1 through 25 a meaningless calculation that would corrupt any rework decision that depends on knowing exactly which wafers are in which state.

---

## Part 4: Understanding Missing Data

Not all missing data is the same. Where the data went missing; and why; changes how you handle it.

### Three Types of Missing Data

| Type | What It Means | Example |
|------|--------------|---------|
| Missing Completely at Random | Gaps with no pattern — just noise | A sensor glitched on random rows |
| Missing at Random | Missingness linked to another variable | Humidity not recorded on night shifts |
| **Missing Not at Random** | **Missingness linked to the missing value itself** | **X6 only recorded when the part passed** |

Missing Not at Random (MNAR) is the most serious. If you ignore those rows, your analysis only sees the passing cases, and every conclusion is biased before you start.

### Missing Data Pattern:- Key Findings

Using **Tables → Missing Data Pattern** on the Explore Missing dataset (882 rows, 7 variables):

| Pattern | Count | What It Means |
|---------|-------|--------------|
| 0000000 | 467 | No missing values complete record |
| 0000001 | 67 | Only X6 missing (7.6% of total) |
| 0000011 | 175 | X5 and X6 both missing |
| 0001111 | 8 | X3, X4, X5, X6 all missing (0.91%) |

**53% of records were complete. X5 had the most missing values at 282 (32%).**

### Proving MNAR:- The X6 Case

When the Distribution chart for Response and X6 was run side by side:
- X6 was recorded as **"Yes" in 100% of cases** when it had a value
- The 252 missing X6 rows aligned **exactly** with the 252 Fail responses
- Clicking the Fail bar in the chart highlighted precisely the rows where X6 was missing

This is not coincidence. X6 was only recorded when a part passed. The missing values are not random gaps they are the failure signal itself.

<img width="1152" height="648" alt="mnar_distribution" src="https://github.com/user-attachments/assets/cef50be0-9db3-42b1-8e20-cc7570363c31" />





## Part 5:  Cleaning Data with Recode

### Making Missing Values Visible

When a variable has missing values, JMP drops those rows from analysis by default. To keep them, the missing values were recoded as the label **"X6-Missing"** using **Cols → Recode**.

**Before recode:** 630 rows analyzed, 252 silently dropped
**After recode:** All 882 rows included, missing values visible as their own category

The result confirmed MNAR: "X6-Missing" and "Fail" had identical counts (252) and identical probability (28.57%).

### Grouping Rare Categories

The Components Raw dataset had 20 customer numbers. Only 6 had more than 5 rows of data. The remaining 14 were grouped into a single **"Other"** category using Recode.

**Result:** 20 cluttered bars → 7 clean, meaningful groups
**Other category total:** 24 rows

---

## Part 6: Building Formulas in JMP

### Scrap Rate (Arithmetic)
```
Scrap Rate = number scrapped ÷ batch size
```
Batch 10038: 37 ÷ 500 = **0.074 (7.4% scrap)**

A negative scrap rate appeared for Batch 10053 (number scrapped = -4). This is physically impossible; flagged as dirty data requiring investigation before inclusion in any analysis.

### Vaccine Era Binning (Conditional Logic)
```
If Year < 1963 → "Before"
Otherwise → "After"
```

| Period | Count | Share |
|--------|-------|-------|
| Before 1963 | 1,712 | 40.7% |
| After 1963 | 2,499 | 59.3% |

### Part Number Extraction (String Formula)
```
Num( Substr( Word(2, Lot, "-"), 2, <length=-1> ) )
```
This formula reads from inside out:
1. **Word**:- pulls the second segment from the lot string after splitting by "-"
2. **Substr**:- removes the first character (the letter "L")
3. **Num**:- converts the remaining text to a usable number

### Elapsed Time (Date Formula)
```
Date Difference(Start Date, End Date, "Day")
```
JMP stores dates as seconds internally. Row 1: 345,600 seconds ÷ 86,400 = **4 days**

### Profit (Join + Formula)
```
Profit = Revenue − Product Cost − Customer Service Cost
```
Row 1: $6,044 − $3,998 − $413 = **$1,632.72**

---

## Part 7: Restructuring Data

### Stack:- Turning Wide Data Into Long Data
The Metal Parts dataset had thickness measurements for 5 parts across 10 hours; one column per hour. To analyze by hour, those 10 columns needed to become rows.

**Before:** 5 rows × 10 columns
**After:** 50 rows × 2 columns (Hour, Thickness)

One important detail: after stacking, the Hour column was stored as text. Sorting alphabetically gave 1, 10, 2, 3... instead of 1, 2, 3...10. The fix was changing Hour to numeric before sorting.

### Concatenate:- Stacking Two Tables
When two tables have the same columns and you want to combine their rows, use Concatenate.

**Profit Q1-Q3:** 18,411 rows + **Profit Q4:** 6,135 rows = **24,546 rows combined**

One important step: make the Q1-Q3 table active before launching Concatenate; otherwise Q4 appears first and the time order is reversed.

### Join: Adding Columns From a Second Table

| Join Method | When to Use | Result |
|-------------|------------|--------|
| By Row Number | Both tables in the same order | Correct 24,546 rows |
| By Matching Columns (wrong here) | When a unique key links rows | Inflated 98,166 duplicate rows |

Using the wrong join method caused a 4× row explosion. The data looked fine but every row was duplicated across multiple matches. This is a silent error;  no warning appears, but every downstream analysis would be wrong.

---

## Part 8:- Key Decisions Reference

| Decision | Use This |
|----------|---------|
| Measurements across multiple columns → one column | **Stack** |
| Two tables, same columns, add more rows | **Concatenate** |
| Two tables, different columns, same rows in same order | **Join by Row Number** |
| Two tables, link rows by a shared ID column | **Join by Matching Columns** |
| Clean inconsistent category labels | **Recode** |
| Group small categories together | **Recode → Group** |
| Replace missing values with a visible label | **Recode → Missing field** |
| Calculate a new variable from existing ones | **Formula Editor** |

---

## Lessons Learned

**1. Always check variable coding before running any analysis.**
A continuous coding on a label column produces output that looks real but means nothing.

**2. Zero does not always mean missing but it might.**
The voltage column was mostly zeros. In this process, zero voltage may be physically impossible. But that decision requires domain knowledge, not just statistics. Never recode without confirming with the process owner.

**3. The join method matters more than it looks.**
Choosing the wrong join turned 24,546 clean rows into 98,166 duplicates. The output table looked fine. The analysis would have been completely wrong.

**4. Missing Not at Random is the most dangerous missing data type.**
Dropping MNAR rows does not just reduce your sample size; it systematically removes one outcome from the analysis. Every result becomes biased toward the remaining group.

**5. Sort order after stacking can silently corrupt time-based analysis.**
Alphabetical sorting of numbers looks fine until you notice 10 comes before 2. Always convert to numeric before sorting stacked time data.

---

## Dataset Summary

| Dataset | Rows | Purpose |
|---------|------|---------|
| Messy Data.jmp | 100 | Identifying all 4 data quality issue types |
| Messy Data 2.jmp | 100 | Distribution and summary statistics practice |
| Components Raw.jmp | 369 | Scrap rate formula, variable coding issues |
| Explore Missing.jmp | 882 | Missing data patterns, MNAR analysis |
| Metal Parts Split.jmp | 50 (after stack) | Stack practice |
| Profit Q1-Q3 + Q4.jmp | 24,546 | Concatenate practice |
| Product Cost + Revenue.jmp | 24,546 | Join practice |
| Batch Records.jmp | — | String extraction formulas |
| Elapsed Time.jmp | 60 | Date and time formulas |
| Measles.jmp | 4,211 | Conditional IF-THEN binning formula |

---

## Course Attribution

Projects in this portfolio were completed as part of the
[JMP Visual Six Sigma Online Statistics Course](https://www.jmp.com/en/online-statistics-course).
All analyses, interpretations, and write-ups are my own.
