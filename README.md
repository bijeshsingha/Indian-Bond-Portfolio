---

# Fixed Income Portfolio Construction: Barbell Strategy Optimization

## 📌 Project Overview

This project focuses on constructing a **risk-neutral fixed income portfolio** designed to thrive in an uncertain and volatile interest rate environment. The strategy employs a **Barbell approach**, concentrating capital in short-term, high-coupon bonds for "Carry" (income) and long-term bonds for "Convexity" (protection and capital appreciation).

The primary objective is to optimize yield while maximizing convexity to protect against large, non-parallel shifts in the yield curve.

---

## 🛠 Methodology: The Three-Phase Framework

### Phase I: Universe Filtering & Valuation

1. **Yield Computation:** Calculated the **Internal Rate of Return (IRR)** and Annualized Yield to establish a "true return" metric across bonds with varying payment frequencies.


2. **Similarity Clustering:** Grouped bonds using a **5% price/maturity band** to isolate idiosyncratic mispricing. This ensures that "excess yield" is the result of market inefficiency rather than term premium.


3. **Rich/Cheap Analysis:** Identified "Cheap" bonds—those with yields above the cluster mean—implying they are undervalued relative to their peers.



### Phase II: Quality & Risk Filtering

* **Liquidity Screening:** Filtered for trading volumes > 20 to avoid "Value Traps" where bonds are cheap simply due to illiquidity.


* **Income Optimization:** Selected high-coupon bonds for the short-end "leg" to maximize cash flow and reduce **Modified Duration**.


* **Barbell Formation:** Intentionally avoided the "Belly" of the curve (intermediate bonds) to focus on the stability of the short end and the explosive upside of the long end.



### Phase III: Convexity & Scenario Testing

To ensure the portfolio is resilient to shocks, I utilized the **Taylor Series expansion** to predict price changes:



* **Duration Effect:** Measures the linear sensitivity to rate changes.


* **Convexity Effect:** Provides "free" risk protection; if rates fall, prices rise faster, and if rates rise, prices fall slower.



---

## 📊 Portfolio Composition

Leg,Allocation,Characteristics,Role in Portfolio
Short Leg,~50% ,"High Coupon, Low Duration ",Income Generator: Provides steady cash flow and low sensitivity to rate hikes. 
Long Leg,~50% ,"High Convexity, High Duration ",Insurance/Upside: Provides protection against rate cuts and non-linear gains via convexity. 

---

## 📈 Key Takeaways

* **Optimized for Volatility:** If rates stay stable, the short leg generates superior carry; if rates become volatile, the long leg's convexity mitigates losses and accelerates gains.


* **Data-Driven Selection:** Every constituent passed a rigorous quantitative filter, moving from gross yield to granular Rich/Cheap valuation adjusted for liquidity and convexity.



---
