# 📊 Measles Vaccine Effectiveness Analysis

## Research Question
Was the measles vaccine program effective at reducing 
the rate of measles infections across all states?

## Background
- MMR vaccine introduced in **1963**
- Data covers **1928–2011**
- **All 50 US states** included
- Data source: 2010 US Census
- Before vaccine: estimated **3-4 million** cases/year

## Answer
**Yes**, the vaccine program was highly effective 
across all states.

## Tools Used
- JMP 17 Pro Graph Builder, Fit Y by X
- Scatterplot with reference line at 1963
- Box Plot by Decade
- Heat Map (State × Year)
- Trellis Plot by Decade

## Key Findings

| Analysis | Finding |
|---|---|
| Scatterplot | Incidence dropped from ~3,000 to near zero after 1963 |
| Box Plot | IQR and outliers collapse from 1970s onward |
| Heat Map | ALL states transitioned from dark to white post-1963 |
| Trellis Plot | Each decade panel shows dramatic reduction post-1963 |

## Timeline
- **Pre-1963:** 3–4 million cases/year nationally
- **1963:** MMR vaccine introduced
- **1963–1970:** Transition gradual adoption
- **1970–1980:** Rapid decline across all states
- **1980–2011:** Near-elimination sustained

## Diagram Analysis

### 1. Scatterplot with 1963 Reference Line
<img width="1152" height="648" alt="01_scatterplot_reference_line" src="https://github.com/user-attachments/assets/8786dfe0-6bf4-4556-8cc9-d19f597751a8" />
### 2. Box Plot by Decade
<img width="1152" height="648" alt="02_boxplot_by_decade" src="https://github.com/user-attachments/assets/a03298e1-7435-4479-ae34-886f122e563c" />
### 3. Heat Map (State × Year)
<img width="1152" height="648" alt="03_heatmap_state_year" src="https://github.com/user-attachments/assets/8301f312-eab1-45ae-8488-572eae9f4c7e" />
### 4. Trellis Plot by Decade
<img width="1152" height="648" alt="02_boxplot_by_decade" src="https://github.com/user-attachments/assets/c6a4db7b-0df6-4f91-9f6b-197347e4c123" />

## Conclusion
The three EDA analyses conclusively show that:
- Every state had **high incidence before 1963**
- Every state transitioned to **near-zero after 1980**
- The decline was **consistent and universal**
- The vaccine program reduced measles by an estimated 
**99%+** across all states within 15–20 years

## Dataset
- **Source:** Measles.jmp — JMP VSS Course Data
- **N:** 4,211 rows
- **Coverage:** All 50 US states, 1928–2011
- **Key Variables:** Yearly Incidence, State Code, 
Year, Decade, Vaccine B4/After
