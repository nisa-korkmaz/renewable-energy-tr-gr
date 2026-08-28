# Renewable Energy & Sustainable Development: A Türkiye–Germany Comparison (1990–2021)

Master's thesis project (Economics & Finance) comparing the long-run and short-run relationship between renewable energy consumption and sustainable development (proxied by the Human Development Index) in Türkiye and Germany, using 32 years of annual macroeconomic data (1990–2021).

## Research Question
Does renewable energy consumption have a statistically significant effect on sustainable development, and does this relationship differ between an emerging economy (Türkiye) and a developed economy (Germany)?

## Data
- **Dependent variable:** Human Development Index (HDI / İGE)
- **Independent variables:** Renewable energy consumption share, GDP growth rate, CO₂ emissions, financial development (bank deposits/GDP), and an energy-policy dummy variable
- **Sources:** Our World in Data, World Bank Data (1990–2021)

## Methodology
Each country was modeled separately using the same variable set:

1. **Unit root testing** — ADF and Phillips-Perron tests to determine stationarity
2. **Structural break testing** — Chow, Bai-Perron, and Zivot-Andrews tests
3. **Multicollinearity diagnostics** — Correlation matrix and Variance Inflation Factor (VIF); high-VIF variables (carbon emissions for Türkiye, financial development for Germany) were dropped
4. **Cointegration testing** — ARDL Bounds test
5. **Model estimation:**
   - **Germany:** Long-run cointegration found → ARDL model + Error Correction Model (ECM)
   - **Türkiye:** No long-run cointegration found → Vector Autoregression (VAR) model for short-run dynamics
6. **Causality testing** — Granger Causality tests
7. **Diagnostic testing** — Breusch-Godfrey (autocorrelation), White test (heteroskedasticity), Jarque-Bera (normality), Ramsey RESET (functional form), CUSUM/CUSUMQ (parameter stability)

## Key Findings
- **Germany:** A statistically significant long-run relationship was found (ARDL Bounds F-statistic = 8.96, exceeding the upper critical bound). The ECM coefficient was negative and significant (-1.06, p < 0.001), indicating the system corrects deviations from long-run equilibrium quickly — consistent with the effectiveness of Germany's *Energiewende* policy.
- **Türkiye:** No long-run cointegration was found (ARDL Bounds F-statistic = 2.12, below the lower critical bound). Short-run VAR results showed that renewable energy consumption and energy policy did not have a statistically significant effect on HDI, while economic growth and financial development showed short-run effects.
- Both country models passed all diagnostic tests (no autocorrelation, no heteroskedasticity, correctly specified functional form), supporting the reliability of the results.

## Repository Contents
- `tr_test_analysis.ipynb` — Full econometric analysis for Türkiye (Python: pandas, statsmodels, arch)
- `ger_test_analysis.ipynb` — Full econometric analysis for Germany (Python: pandas, statsmodels, arch)

## Tools
Python (pandas, numpy, statsmodels, arch, scipy, seaborn, matplotlib, ruptures)

---
*This thesis was completed as part of a Master's degree in Economics and Finance at Istanbul Yeni Yüzyıl University (2025).*
