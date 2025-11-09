# 🏠 Home Away From Home: Airbnb Occupancy Analysis

**Module:** IS630 – Statistical Thinking in Data Science  
**Institution:** Singapore Management University (MITB – Analytics Track)  
**Date:** November 2025  
**Authors:** Tanisha Kaur, Priya Latha, Bao Sihan, Bai Haotian, Hor Wen Xuan, Serene Cheng  

---

## 📘 Project Overview
This project investigates the **key drivers of Airbnb occupancy** in Sydney, Australia, using data analytics and multiple linear regression.  
Our goal was to identify which listing and host attributes most strongly influence occupancy rate, and to propose evidence-based recommendations for Airbnb and hosts.

**Core question:**  
> What variables are associated with high Airbnb occupancy rates?

---

## 🎯 Objectives
- Quantify the relationship between listing attributes (price, amenities, reviews, etc.) and occupancy.  
- Identify controllable factors that hosts can optimize to improve booking rates.  
- Provide actionable recommendations to Airbnb to strengthen host engagement and pricing strategy.

---

## 🧩 Dataset
- **Source:** [Inside Airbnb](https://insideairbnb.com) – public data on Sydney listings.  
- **Size:** 18,187 rows × 79 columns (filtered to 6,434 active listings).  
- **Selected features:**
  - Host response rate / time / acceptance rate  
  - Superhost status, verified identity  
  - Instant bookable, license validity  
  - Review score rating  
  - Price (AUD), accommodates, amenities count  
  - Minimum / maximum nights  

---

## 🧹 Data Preparation
1. **Filtered listings** with insufficient booking history.  
2. **Cleaned variables:** stripped symbols (“$”, “%”), converted to numeric.  
3. **Handled missing values:** coded booleans for license and Superhost.  
4. **Feature engineered amenities** variable as amenity count per listing.  
5. **Derived occupancy rate** as (estimated occupied days ÷ 365).  
6. **Transformed skewed variables** using log transformation; applied 99th percentile cutoff for outliers.  

---

## 📊 Methodology
We applied **Multiple Linear Regression (MLR)** to model the log-transformed occupancy rate as a function of listing and host attributes.

**Model performance:**
- Adjusted R² = 0.292  
- F-statistic p-value < 0.001  
- All key predictors significant (p < 0.001)  

**Assumption checks:**
- ✅ No multicollinearity (VIF < 10)  
- ✅ Normal residuals (Durbin-Watson ≈ 1.93)  
- ⚠ Non-constant variance → corrected using robust standard errors  
- ⚠ Non-linearity → corrected via log transformation  

---

## 📈 Key Findings

| Variable | Effect on Occupancy | Interpretation |
|-----------|--------------------|----------------|
| **Review Score Rating** | +0.657 | 1-point increase → ~93% higher occupancy |
| **Superhost Status** | +0.323 | Superhosts enjoy ~38% higher occupancy |
| **Accommodates (log)** | +0.272 | 1% increase in capacity → +0.27% occupancy |
| **Host Acceptance Rate** | +0.020 | 1% increase → +2% occupancy |
| **Amenities Count** | +0.0057 | Each extra amenity → +0.57% occupancy |
| **Minimum Nights** | +0.0154 | Each extra minimum night → +1.5% occupancy |
| **Price (log)** | −0.439 | 1% increase → −0.44% occupancy |
| **Bathrooms** | −0.127 | Each extra bathroom → −13% occupancy |

---

## ⚙️ Technical Tools
- **Python:** pandas, numpy, matplotlib, seaborn, statsmodels  
- **Notebook:** `CleanAirbnb5Nov.ipynb`  
- **Statistical Techniques:** data cleaning, transformation, regression, diagnostics (VIF, DW, residual plots)

---

## 💡 Management Recommendations
1. **Host Support Dashboard:** enable hosts to track reviews and improve service quality.  
2. **Superhost Incentives:** promote benefits of achieving Superhost status.  
3. **Dynamic Pricing System:** implement ML-based price suggestions and event-based alerts.  

---

## ⚠️ Data Limitations
- Occupancy estimated via review-to-stay proxy (~50% conversion).  
- Missing data for photo quality, dynamic pricing, and textual description.  
- Modest model fit (R² = 0.292) due to omitted variables and market volatility.

---

## 🧭 Conclusion
The analysis reveals that **trust, credibility, and service quality** (Superhost, reviews) are the strongest predictors of occupancy.  
Our study provides actionable insights for Airbnb and hosts to **optimize listings, pricing, and service quality** using data-driven strategies.

---

## 🧰 Repository Structure
