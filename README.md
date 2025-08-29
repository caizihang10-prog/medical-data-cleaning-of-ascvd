# Omega-3 × Na/K and ASCVD risk（NHANES 2013–2023）

> Cross-sectional analysis using NHANES complex survey design.  
> Goal: test whether **omega-3 intake** and **sodium/potassium ratio (Na/K)** interact on ASCVD risk.

## Overview
- Collated and cleaned multi-cycle NHANES (2013–2023) dietary, exam and lab data; computed **ASCVD 10-year risk (PCE)** for eligible adults; analysed **omega-3 (EPA+DHA, per 1000 kcal)**, **Na/K (per 1000 kcal)** and their **interaction**.
- Outputs: correlation heatmap, linear model (ASCVD continuous), logistic model (high risk ≥7.5%).

## Methods (brief)
- **Design**: NHANES complex sampling with strata/PSU/weights; cycles pooled with combined weights.  
- **Exposures**: omega-3 (EPA+DHA, g/1000 kcal), Na/K (mg/mg per 1000 kcal); both z-scored & centred.  
- **Outcome**: ASCVD 10-year risk (PCE, age 40–79), plus hs-CRP, lipids, SBP/DBP.  
- **Models**:  
  - Linear: `ASCVD = β0 + β1·Z(ω3) + β2·Z(NaK) + β3·Z(ω3)×Z(NaK) + covariates`  
  - Logistic (High risk ≥7.5%): `logit(p) = ...` (same terms)  
- **Covariates**: age, sex, race/ethnicity, education, income, BMI, smoking, alcohol, total energy, meds.  

## Figures
<p align="center">
  <img src="figures/relation.jpg" width="560" alt="Correlation heatmap">
  <br><em>Fig 1. Correlation heatmap (key variables).</em>
</p>

<p align="center">
  <img src="figures/na_k_ratio_vs_asvcd_risk.png" width="560" alt="Na/K vs ASCVD (linear)">
  <br><em>Fig 2. Na/K vs ASCVD (linear model).</em>
</p>

<p align="center">
  <img src="figures/logistic_regression.png" width="560" alt="Logistic model (High risk ≥7.5%)">
  <br><em>Fig 3. Logistic regression for high ASCVD risk (≥7.5%).</em>
</p>

## Columns (click to expand)
<!-- 建议把“列名芯片式/三列表”片段粘到这里（此前我已为你生成 headers_chips.html / headers_table.md） -->
<details>
  <summary><b>Show column names</b></summary>

| Column 1 | Column 2 | Column 3 |
| --- | --- | --- |
| SEQN | DR1DRSTZ | DR1TKCAL |
| DR1TSODI | DR1TPOTA | DR1TSFAT |
| DR1TMFAT | DR1TPFAT | DR1TCHOL |
| DR1TFIBE | DR1TVC | DR1TATOC |
| DR1TBCAR | DR1TFOLA | Source_File_x |
| DR1IP182 | DR1IP225 | RIDAGEYR |
| RIAGENDR | RIDRETH1 | LBXTC |
| LBDHDL | BPXSY2 | BPQ030 |
| SMQ020 | DIQ010 | Source_File_y |
| ASCVD_Risk | Total_Omega3 | Omega3_per_1000kcal |
| Na_K_Ratio | Na_K_Ratio_per_1000kcal |  |

</details>

## Repo shortcuts
- `figures/` – exported PNG/JPG used in README  
- `notebooks/` – analysis notebooks (optional)  
- `tables/` – summary CSVs/MD tables (optional)

## Limitations
Cross-sectional design; dietary recall error; residual confounding.  
