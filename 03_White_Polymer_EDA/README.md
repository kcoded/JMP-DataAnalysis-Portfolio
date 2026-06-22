# White Polymer VSS Team Data : EDA & Script Automation in JMP

**Tool:** JMP 17 Pro  
**Dataset:** White Polymer VSSTeamData.jmp  
**Rows:** 110 total | 5 excluded | 5 hidden  
**Variables:** Batch Number, Yield, MFI, CI, SA, M%, Xf, pH, Viscosity, Ambient Temp, Quarry, Shift

---

## What This Project Is About

This project uses a white polymer manufacturing dataset to practice two things:
1. **Exploring the data** looking at distributions and relationships between key process variables like Yield, MFI, and Ambient Temperature
2. **Automating analysis in JMP**  saving, grouping, and combining scripts so that a full set of analyses can be re-run in a single click

---

## Questions Solved

### Q1:- Can I save and group multiple analyses to run together?

**What I did:**
- Built histograms and summary statistics for Yield and MFI, then saved that analysis as a script to the data table
- Built a scatterplot of Yield vs. MFI and saved that as a second script
- Selected both scripts in the data table, right-clicked, and chose **Group Scripts**

**What happened:**
Running the group script fired both analyses at once, the distributions and the scatterplot appeared together in a single action.

**What the data showed:**
- MFI was very tightly controlled (mean ≈ 198.15, Std Dev = 2.11)
- Yield was far more variable (mean ≈ 89.3%, Std Dev ≈ 9.85%), suggesting batch-to-batch inconsistency worth investigating

---

### Q2:- Save the data table with all scripts stored inside it

Saved the file as `VSSTeamDataMichael.jmp` via File → Save As. All grouped scripts are embedded in this file.

---

### Q3:- Can I combine two scripts into one script window?

**What I did:**
- Built histograms and summary statistics for MFI and Ambient Temp, saved to a script window
- Built a scatterplot of MFI vs. Ambient Temp, saved to the **same** script window
- Ran the combined script

**What happened:**
JMP automatically separated the two scripts with a semicolon (`;`) in the script window. Running it produced both analysis windows simultaneously, the distributions and the scatterplot appeared at the same time.

**What the data showed:**
- Ambient Temp ranged widely (5.31 to 24.97), meaning batches were made under very different environmental conditions
- Despite this wide range, MFI stayed stable no obvious relationship between Ambient Temp and MFI

---

### Q4:- Save the combined script as a file

Saved the script window as `VSS Scripts Michael.jsl` via File → Save Script. This file can be opened and run independently of the data table.

---

### Q5:- Add an external script into the data table

**What I did:**
- Opened `VSS Scripts Michael.jsl`
- Used File → Save Script to Data Table to embed it directly into the data table
- Named it **VSS Scripts Michael Analysis**

**What happened:**
Clicking the green triangle next to the script in the data table ran both analyses, distributions and scatterplot — in one click, without needing to open the `.jsl` file at all.

---

### Q6"- Build a Dashboard combining both outputs

**What I did:**
- Ran the saved script to generate the two analysis windows
- Used **Window → Combine Windows** to merge them into a single dashboard layout
- Saved the dashboard script back to the data table

**What happened:**
Running the dashboard script from the data table now opens everything in one unified window:

![Dashboard](https://github.com/user-attachments/assets/ce4d46d4-d618-4b14-9e0b-b63eb1bbfa24)

- **Left:** Scatterplot of MFI vs. Ambient Temp
- **Right:** Distributions with histograms, boxplots, and summary statistics for MFI and Ambient Temp

One click. One window. Everything.

---

## JMP Skills Demonstrated

| Skill | What It Means |
|-------|--------------|
| Distribution Platform | Building histograms, boxplots, and summary stats |
| Graph Builder | Building scatterplots |
| Script Saving | Storing analyses inside the data table or as `.jsl` files |
| Script Grouping | Running multiple saved analyses with one click |
| Script Combining | Merging analyses into one script using semicolons |
| Dashboard Creation | Combining multiple output windows into one view |
| Script Automation | Reproducing a full analysis workflow instantly |

---

## Files in This Project

| File | What It Is |
|------|-----------|
| `VSSTeamDataMichael.jmp` | JMP data table with all scripts saved inside |
| `VSS Scripts Michael.jsl` | Standalone JMP script file for MFI and Ambient Temp analyses |
| `images/dashboard.png` | Screenshot of the combined dashboard output |
| `images/yield_mfi_distributions.png` | Yield and MFI distribution outputs |
| `images/scripts_panel.png` | Data table showing grouped scripts |

---

## Course Context

Part of the **JMP Visual Six Sigma (VSS) Online Course**.  
This builds toward my goal of applying statistical process control and machine learning to semiconductor manufacturing.

> **Course:** [JMP Visual Six Sigma](https://www.jmp.com/en/online-statistics-course) | **Tool:** JMP 17 Pro
