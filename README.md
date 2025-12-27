# AgriSmart: AI-Driven Irrigation Demand Forecasting

## 📌 Context & Overview
Water scarcity and energy optimization are critical challenges for solar-powered irrigation in West Africa. This project, which served as the foundation for the **AgriSmart** system (Regional Finalist at CATAL1.5T West Africa Climathon 2025), aims to predict daily water requirements for off-season tomato crops to optimize reservoir management and autonomous irrigation scheduling.

## 🎯 Objectives
* **Water Demand Estimation:** Modeling irrigation needs based on multivariate bioclimatic variables.
* **Comparative Modeling:** Evaluating different machine learning architectures for precision agriculture.
* **Phenological Integration:** Testing the impact of dynamic Crop Coefficients (Kc) on prediction accuracy.

## 📊 Data & Physics-Based Feature Engineering
* **Source:** NASA POWER (Satellite-derived meteorological data).
* **Timeframe:** January 2020 – August 2025 (726 daily observations).
* **Raw Variables:** $T_{min}$, $T_{max}$, Rainfall, Solar Radiation, Specific Humidity.
* **Derived Variables (Feature Engineering):** * Reference Evapotranspiration ($ET_0$) calculated via the **Hargreaves Method**.
  * Crop Evapotranspiration ($ET_c = ET_0 \times K_c$).
  * Irrigation Water Requirement ($IWR$).



## 🛠️ Methodology & Tech Stack
* **Language:** Python 
* **Tools:** Scikit-learn, Pandas, NumPy, Matplotlib.
* **Simulation:** Crop data (tomato) parameters derived from **FAO CROPWAT 8.0** standards (Planting: Nov 1st; Harvest: March 25th).

### Workflow:
1. **Data Preprocessing:** Cleaning and temporal alignment of NASA POWER datasets.
2. **Exploratory Data Analysis (EDA):** Correlation analysis between radiation, temperature, and $ET_0$.
3. **Modeling:** Implementation of regression algorithms to map climatic inputs to water demand.
4. **Validation:** Comparative testing of constant vs. interpolated Kc values.

## 🚀 Key Results
The model demonstrated high precision in simulating the water-soil-vegetation nexus:
* **Constant Kc (0.85):** Achieved a **RMSE of 0.098 mm**, showing excellent baseline stability.
* **Interpolated Dynamic Kc:** Achieved a **RMSE of 0.157 mm**.
* **Conclusion:** The results validate the feasibility of a low-cost, AI-driven irrigation controller for smallholder farmers.



## 🔮 Perspectives for Improvement
* **Advanced Physics:** Transitioning from Hargreaves to the **FAO-56 Penman-Monteith** method for higher physical accuracy.
* **Stage-Weighting:** Implementing attention-based weighting for critical growth stages (Flowering/Fruiting).
* **Deep Learning:** Exploring **LSTM** or **GRU** networks to better capture the temporal memory of soil moisture depletion.

---
*Project recognized as a Regional Finalist at the CATAL1.5T West Africa Climathon.*
