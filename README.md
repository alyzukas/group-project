# Renewable Energy and Carbon Emissions: A Panel Data Analysis (2010–2024)

> Investigating whether increases in the share of renewable energy production lead to measurable reductions in national CO₂ emissions. 

---

## Project Overview

This project analyzes whether increasing the renewable share of a country’s electricity generation is associated with lower per-capita CO₂ emissions.
We build a country–year panel dataset (2010–2024) combining renewable electricity generation, electricity demand, GDP per capita, population, and CO₂ emissions.

Using fixed-effects panel regression, lag analysis, and robustness checks, we estimate the relationship between renewable energy adoption and emissions while controlling for economic activity and unobserved country differences. 

- **Objective:** Determine whether increasing the renewable share of national energy supply corresponds with lower CO₂ emissions per capita.  
- **Domain:** Sustainability / Environmental Data Science / Energy Economics  
- **Key Techniques:** Fixed-effects panel regression, lag analysis, robustness checks

---

## Project Structure

```
├── data/                 # Raw and processed data (CSV files)
├── code/                 # Jupyter notebooks and Python scripts
├── reports/              # Generated reports and visualizations
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

---

## Data

### 1. Energy Institute Statistical Review of World Energy (2024/2025)
- Electricity generation by fuel (TWh)  
- Renewable generation (solar, wind, geothermal, bioenergy)  
- Hydropower production  

### 2. Global Carbon Atlas  
- Annual CO₂ emissions (MtCO₂)  
- Population data  
- Derived: CO₂ per capita (metric tons per person)

### 3. World Bank (WDI)  
- GDP per capita (constant USD)

- **Data Format:** CSV files (annual, country-level observations).  
- **Data Preparation:** Merging datasets by country and year, converting units to metric tons per capita, handling missing values, and normalizing scales.   

---

## Analysis

We conduct a quantitative, correlational analysis using a country-year panel dataset.  

**Steps include:**
1. Initial analysis of baseline relationships between key variables.  
2. Top 10 and Bottom 10 – Compare global renewable share levels across regions in 2010-2024. 
3. Analyze the relationships between renewable energy share per capita, CO₂ emissions per capita, and GDP per capita in 2010-2024 (Panel Regression Model).
4. Analyze whether renewable energy reduces carbon emissions immediately, or whether the benefits show up over time (Lag Analysis).
5. Check whether our main findings are reliable and don’t disappear when we change assumptions, model structure, or variable definitions (Robustness Testing). 
6. Analyze whether renewable energy shares reduce emissions even while economies grow (Expansion Analysis).

**Reproduction order:**
1. `data_preprocessing.ipynb` — Import and clean datasets.  
2. `exploratory_analysis.ipynb` — Generate descriptive and correlation visualizations.  
3. `regression_model.ipynb` — Run panel regressions and infer relationships.  
4. `results_summary.ipynb` — Summarize findings and export visualizations.

---

## Results

### **Fixed-Effects Model**
- The coefficient on **renewable_share_pct** is **negative and statistically significant**.
- Interpretation: Increasing renewable share **reduces per-capita CO₂ emissions**, holding GDP and fixed effects constant.

### **Lag Analysis**
- **Current-year renewable share:** significant negative effect  
- **1-year lag:** also negative and significant  
- **2-year lag:** negative but not significant  
- Interpretation: Renewable expansion lowers emissions, with the strongest impact in the current and following year.

### **Robustness Checks**
- Removing extreme outliers produces **nearly identical coefficients**.  
- Alternative functional form (log of renewable share) also yields negative, significant results.  
- Conclusion: Findings are **highly stable and not driven by a small number of countries**.
 

---

## Tools & Technologies

- Python 3  
- pandas, numpy  
- matplotlib, seaborn  
- statsmodels (regression with clustered SEs)  
- linearmodels (panel data estimation)

---

## Limitations

- Observational data → cannot infer strict causality   
- Differences in country reporting quality  
- Limited ability to model nonlinear threshold effects  

---

## References

1. Intergovernmental Panel on Climate Change (IPCC). (2011). Renewable Energy Sources and Climate Change
Mitigation: Special Report of the Intergovernmental Panel on Climate Change (SRREN). Cambridge University Press.
https://www.ipcc.ch/report/renewable-energy-sources-and-climate-change-mitigation/Wang, Q., & Zhao, M.
(2023). Can renewable energy investment reduce carbon dioxide emissions? Evidence from scale and structure.
Energy Economics, 112, 106215. https://www.sciencedirect.com/science/article/abs/pii/S0140988322003334A
theoretical paper that addresses one of our core questions by linking the renewable energy investment to CO₂
emissions while decomposing effects into scale, technique, and structure.
2. Liu, Y., Zhang, H., & Li, X. (2023). The effect of clean energy investment on CO₂ emissions. Energy Economics, 123,
107048. https://www.sciencedirect.com/science/article/pii/S014098832300498XA recent study published by Science
Diet, diving into quantifying the elasticity between clean energy investment and emissions.
3. Chen, Z., Li, F., & Wu, S. (2022). The effect of renewable energy on carbon emissions through globalization. Frontiers
in Environmental Science, 10, 960795. https://www.frontiersin.org/articles/10.3389/fenvs.2022.960795/fullPublished
by PMC Central, this report assesses direct and indirect (mediated) effects of renewable energy on emissions
4. Bölük, G., & Mert, M. (2014). Fossil and renewable energy consumption, economic growth, and carbon emissions: An
empirical analysis. Energy Policy, 74, 471–479. https://ideas.repec.org/a/eee/energy/v74y2014icp439-
446.htmlProvides us with panel data for the period of 1990-2008.
5. Ozturk, I., & Acaravci, A. (2013). The long-run and causal analysis of energy, growth, openness, and financial
development on carbon emissions in Turkey. Energy Economics, 36, 262–267.
https://econpapers.repec.org/RePEc:eee:eneeco:v:36:y:2013:i:c:p:262-267 

---

## Authors

- **Alyssa Zukas** — [alyzukas@seattu.edu](mailto:alyzukas@seattu.edu)  
- **Ben Jessop** — [bjessop@seattleu.edu](mailto:bjessop@seattleu.edu)  
- **Travis St Peter** — [tstpeter@seattleu.edu](mailto:tstpeter@seattleu.edu)  

---

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- Seattle University – *DATA 5100: Foundations of Data Science (Fall 2025)*  
- Global Carbon Atlas, IEA, World Bank, Energy Institute, and NREL for open data resources  
- Python open-source community for enabling reproducible scientific analysis  

