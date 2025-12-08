# Renewable Energy and Carbon Emissions: A Cross-Country Analysis (2010–2024)

> Analyzing whether countries with a higher share of renewable energy in their total energy supply emit less CO₂ per capita.

---

## Project Overview

Global CO₂ emissions continue to rise despite record investments in renewable energy. This project investigates whether a **higher share of renewable energy in total energy supply** is associated with **lower per-capita carbon emissions**.  

The analysis uses international, country-level data (2000–2023) to examine how renewable electricity share relates to total and per-capita CO₂ emissions. By quantifying this relationship, the project aims to shed light on the **real-world effectiveness of renewable energy transitions** in reducing emissions and to identify regional variations in outcomes.  

- **Objective:** Determine whether increasing the renewable share of national energy supply corresponds with lower CO₂ emissions per capita.  
- **Domain:** Sustainability / Environmental Data Science / Energy Economics  
- **Key Techniques:** Panel regression, correlation analysis, clustering, changepoint analysis, visualization  

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

- **Primary Sources:**
  1. [Global Carbon Atlas](https://globalcarbonatlas.org) — CO₂ emissions by country (total, per capita, and per GDP).  
  2. [International Energy Agency (IEA) Global Energy Review 2025](https://www.iea.org/reports/global-energy-review-2025) — Global CO₂ and energy statistics.  
  3. [World Bank World Development Indicators (WDI)](https://databank.worldbank.org/source/world-development-indicators) — Renewable electricity share, GDP, and population.  
  4. [Energy Institute Statistical Review of World Energy 2025](https://www.energyinst.org/statistical-review) — Energy demand and supply by fuel and region.  
  5. [National Renewable Energy Laboratory (NREL) 100% Clean Electricity Study](https://www.nrel.gov/analysis/100-percent-clean-electricity-by-2035-study.html) — Scenario analysis of decarbonization pathways.

- **Data Format:** CSV files (annual, country-level observations).  
- **Data Preparation:** Merging datasets by country and year, converting units to metric tons per capita, handling missing values, and normalizing scales.  
- **Estimated Size:** ≤10,000 rows (≈200 countries × 40 years).  

---

## Analysis

We conduct a **quantitative, correlational analysis** using a **country-year panel dataset**.  

**Steps include:**
1. **Descriptive analysis:** Summary statistics, scatterplots, and time-series trends.  
2. **Correlation analysis:** Identify relationships between renewable share and emissions metrics.  
3. **Panel regression:** Estimate associations while controlling for GDP and year effects.  
4. **Optional extensions:**  
   - **Clustering** countries by energy mix and emissions trajectory.  
   - **Changepoint detection** to identify inflection points following renewable adoption.  

**Reproduction order:**
1. `data_preprocessing.ipynb` — Import and clean datasets.  
2. `exploratory_analysis.ipynb` — Generate descriptive and correlation visualizations.  
3. `regression_model.ipynb` — Run panel regressions and infer relationships.  
4. `results_summary.ipynb` — Summarize findings and export visualizations.

---

## Results

Preliminary expectations are that:
- Countries with **higher renewable energy shares** will tend to exhibit **lower per-capita CO₂ emissions**, though the strength and consistency of the relationship may vary by region and economic structure.  
- There may be **time delays** between renewable adoption and measurable reductions in emissions.  
- **GDP and energy demand** are expected to moderate the observed associations.  

---

## Tools & Technologies

- **Language:** Python  
- **Libraries:** pandas, NumPy, matplotlib, seaborn, statsmodels, scikit-learn  
- **Environment:** Jupyter Notebook  

---

## Challenges

1. **Causality:** Establishing causal interpretation beyond correlation.  
2. **Data completeness:** Missing or inconsistent data for developing countries.  
3. **Interpretation:** Ensuring visualizations and results are contextualized and responsibly communicated.  

Sensitivity checks and transparent discussion of assumptions will be incorporated throughout.

---

## References

- Wang, Q., & Zhao, M. (2023). *Can renewable energy investment reduce carbon dioxide emissions?* *Energy Economics, 112*, 106215.  
- Bölük, G., & Mert, M. (2014). *Fossil and renewable energy consumption, economic growth, and carbon emissions.* *Energy Policy, 74*, 471–479.  
- Ozturk, I., & Acaravci, A. (2013). *The long-run and causal analysis of energy, growth, openness, and financial development on carbon emissions in Turkey.* *Energy Economics, 36*, 262–267.  
- IPCC (2011). *Renewable Energy Sources and Climate Change Mitigation: Special Report.*  
- Liu, Y., Zhang, H., & Li, X. (2023). *The effect of clean energy investment on CO₂ emissions.* *Energy Economics, 123*, 107048.  

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

