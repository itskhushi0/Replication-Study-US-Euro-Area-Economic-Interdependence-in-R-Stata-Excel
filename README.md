# Replication-Study-US-Euro-Area-Economic-Interdependence-in-R-Stata-Excel


This project replicates and extends research on the **asymmetric economic relationship** between the U.S. and the Euro Area. While the U.S. is often viewed as largely self-contained, this study highlights how trade flows, financial markets, and expectations create a cycle where shocks in one region quickly affect the other.

---

## 1. Project Overview

- **Goal:** Examine how economic shocks transmit between the U.S. and Euro Area.  
- **Identification Challenge:**  
  - The original study used a **Structural Vector Error Correction Model (VECM)**.  
  - Identification was performed **manually, equation-by-equation using OLS**, embedding theoretical assumptions rather than relying on automated routines.  

---

## 2. The Dataset: Historical Reconstruction

- **Time period:** 1983 Q1 – 2007 Q4 (post-Volcker U.S. and Euro introduction era).  
- **Euro Area construction:**  
  - For pre-1999 data, a **sliding weight mechanism** (Anderson et al., 2011) approximated the monetary union.  
- **Price level scaling:**  
  - Inflation converted to **quarterly log changes** (annual % ÷ 400).  
  - Log price levels constructed cumulatively, starting at ln(100), matching the original study.  
- **Stationarity:**  
  - Tests (ADF and Phillips-Perron) confirmed that **log output (y_us, y_eu) and real exchange rate (lnRER) are I(1)**.  
  - Inflation and interest rates treated as stationary.  

---

## 3. Methodology: Technical Execution

- **Model variables:**  

Y_t = [y_us, y_eu, π_us, π_eu, r_us, r_eu, lnRER]′

- **Cointegration:**  
- Johansen Trace Test rejects no-relationship null hypothesis.  
- **Rank r=1** selected to represent a single long-run equilibrium.  
- **Equilibrium adjustment (α):**  
- **U.S. output, U.S. inflation, and real exchange rate** are the main variables restoring balance after shocks.  
- **Cholesky ordering (recursive):**  

y_us → y_eu → π_us → π_eu → r_us → r_eu → lnRER

- Assumes earlier variables affect later ones instantly, but not vice versa.  

---

## 4. Key Findings: Shock Transmission Patterns

- **Shock focus:** Only **supply/output shocks** have permanent effects.  
- **Standardized shock sizes:**  
- Output: 0.0046  
- Inflation: 0.49  
- Interest rates: 0.34  
- **Currency appreciation:**  
- A permanent output shock causes local currency appreciation.  
- Inflation shocks also cause currency appreciation (empirically robust but not theoretically obvious).  
- **Output spillovers:**  
- U.S. output shock → strong positive effect on Euro Area GDP.  
- Euro Area output shock → insignificant or negative effect on U.S. GDP.  
- **Monetary proactivity:** Foreign central banks react to imported inflation by raising interest rates.  

---

## 5. Extension: Structural Stability & the ECB

- **Objective:** Investigate how monetary policy spillovers changed after the Euro (1999 Q1).  
- **Pre-Euro (1983–1998):**  
- U.S. interest rate shocks caused a **robust, long-lasting reaction in Europe**, peaking at 0.30 and significant for 20 quarters (5 years).  
- **Post-Euro (1999–2007):**  
- Peak response **halved to 0.15** and lost significance after 8 quarters (2 years).  
- **Conclusion:** ECB independence **reduced Europe’s sensitivity** to U.S. interest rate shocks, insulating financial conditions.  

---

## 6. Project Conclusion: Asymmetry and Autonomy

- **U.S. leads Euro Area:** The U.S. economy continues to drive Euro Area activity, but effects are asymmetric.  
- **Financial channels:** Exchange rate movements transmit “imported inflation,” requiring central bank responses.  
- **Monetary autonomy:** The Euro strengthened Europe’s ability to resist U.S.-led interest rate cycles, enhancing policy independence post-1999.  
