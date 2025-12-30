---

# Fixed Income Portfolio Optimization: A Quantitative Barbell Strategy

### 📊 Project Overview

This project constructs a risk-optimized fixed income portfolio within the **Indian Corporate Bond Market**. By employing a **Barbell Strategy**, the portfolio seeks to balance liquidity and income ("Carry") from short-term assets with the non-linear upside ("Convexity") of long-term assets.

The selection process utilizes a rigorous quantitative filter, utilizing **K-Means style clustering** to identify idiosyncratic mispricing and **Taylor Series expansions** to stress-test portfolio sensitivity to interest rate shocks.

###  Investment Objective

* **Primary Goal:** Construct a risk-neutral portfolio that optimizes yield while maximizing convexity.
* **Market Outlook:** Uncertain/Volatile Interest Rate Environment.
* **Strategy:** **Long/Short Volatility Optimization** (Barbell).
* *Short Leg (~60%):* High Coupon, Low Duration (Income Generator).
* *Long Leg (~40%):* High Convexity, High Duration (Capital Appreciation/Hedge).

---

### ⚙️ Methodology

The portfolio construction followed a three-phase quantitative pipeline:

#### Phase I: Universe Filtering & Valuation

1. **Yield Computation:** Calculated Internal Rate of Return (IRR) and Annualized Yield to establish a baseline "true return" metric beyond nominal coupon rates.
2. **Similarity Clustering:** Grouped bonds into "Similarity Clusters" using a 5% Price/Maturity band. This isolates **idiosyncratic mispricing**, ensuring excess yield is due to market inefficiency rather than structural differences.
3. **Rich/Cheap Analysis:** Calculated the Mean Yield per cluster. Bonds trading significantly above the cluster mean were flagged as "Cheap" (undervalued).

#### Phase II: Quality & Risk Filtering

* **Liquidity Screening:** Filtered for Trading Volume > 20 to avoid "Value Traps" and liquidity premiums.
* **Income Screening:** Prioritized high-coupon bonds for the short leg to reduce Modified Duration and stabilize immediate price volatility.

#### Phase III: Convexity Optimization & Stress Testing

* **Convexity Selection:** Among bonds with similar Duration, assets with higher **Convexity** were selected to provide "free" risk protection (slower fall when rates rise, faster rise when rates fall).
* **Mathematical Stress Test:** Used the **Taylor Series Expansion** to predict price changes () under various interest rate shocks ():

*Where  is Modified Duration and  is Convexity.*

---

### 📈 Portfolio Performance & Composition

**Current Status:**

* **Total Investment:** ₹12,309.93
* **Current Value (MTM):** ₹12,767.48
* **Total Unrealized PnL:** **+6.76%** (Absolute)
* **Portfolio Duration:** ~3.26 Years

**Top Performing Assets:**
| Asset | Maturity | Coupon | Strategy Role | Gain % |
| :--- | :--- | :--- | :--- | :--- |
| **Nido Home Finance** | 2035 | 11.0% | Long Leg (Convexity) | **+27.11%** |
| **Nuvama Wealth** | 2030 | 10.25% | Short Leg (Yield) | **+7.58%** |

---

### 🛠️ Technologies Used

* **Python:** Data analysis and calculation logic.
* **Pandas:** Data manipulation, yield calculation, and filtering.
* **NumPy:** Financial mathematics (IRR, NPV) and Taylor Series implementation.
* **Excel:** Data sourcing and final reporting.
* **Data Sources:** Refinitiv, TradingView, LSEG.

---

### 🚀 Future Improvements

* **Sector Diversification:** The current portfolio has high exposure to NBFCs (Non-Banking Financial Companies). Future iterations will incorporate constraints to cap sector exposure at 30%.
* **Automated Rebalancing:** Implement a Python script to trigger rebalancing alerts when the duration drift exceeds a specific threshold (e.g., +/- 0.5 years).
* **VaR Implementation:** Calculate Value at Risk (VaR) to quantify maximum potential loss over a specific time frame.

---

### 👨‍💻 About the Author

**Bijesh Singha**

* **MBA in Finance & Data Science** | Great Lakes Institute of Management
* **B.Tech in Mechanical Engineering** | NIT Silchar
* **Ex-QA Engineer** | LTIMindtree
* **Focus:** Bridging the gap between engineering precision and financial strategy.

---
