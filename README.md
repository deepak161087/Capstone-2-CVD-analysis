# Capstone Project: Environmental and Socioeconomic Factors Impacting Cardiovascular Disease (CVD) in California

This project investigates the relationship between environmental exposures, social vulnerabilities, and cardiovascular disease (CVD) prevalence across communities in California.

Using the **CalEnviroScreen 4.0** dataset, which compiles detailed metrics at the census-tract level, the analysis explores how factors such as air quality (e.g., PM2.5, ozone), pollution exposure (e.g., diesel particulate matter, toxic releases), and demographic pressures (e.g., poverty, housing burden, linguistic isolation) contribute to disparities in cardiovascular health outcomes.

---

## Data Source

📂 **CalEnviroScreen 4.0 (OEHHA, California Office of Environmental Health Hazard Assessment)**  
- Link: [https://oehha.ca.gov/calenviroscreen/report/calenviroscreen-40](https://oehha.ca.gov/calenviroscreen/report/calenviroscreen-40)  
- Over 80 environmental, health, and demographic variables for 8,000+ census tracts in California.  
- Includes:
  - Environmental indicators: ozone, PM2.5, diesel particulate matter, toxic releases.
  - Population health data: asthma rates, low birth weight, cardiovascular disease.
  - Demographic factors: poverty, educational attainment, housing burden, linguistic isolation.

---

## Project Goals

- Understand the **spatial and statistical patterns of cardiovascular disease** across California.  
- Identify **environmental and socioeconomic factors most strongly correlated with CVD rates**.  
- Build a **baseline regression model to predict CVD risk** based on these factors.  
- Inform **public health and environmental justice efforts** by identifying high-risk communities.

---

## Summary of Findings

### Polynomial Ridge Regression Model

- The optimized polynomial Ridge regression model (degree 2) with best alpha = 100 demonstrates strong predictive performance:
  - Cross-validated RMSE: 3.697  
  - Test RMSE: 3.760  
  - Test R²: 0.43, indicating that the model explains 43% of the variance in cardiovascular disease rates.
- **Education** is the most influential predictor, exhibiting both strong linear and nonlinear effects (notably Education²).
- Other important contributors include **Poverty, Ozone levels, Linguistic Isolation,** and **Unemployment**, highlighting the combined impact of social vulnerabilities and environmental exposures.
- Significant interaction terms such as **PM2.5 × Groundwater Threats**, **Diesel PM × Poverty**, and **PM2.5 × Traffic** reveal multifactorial influences on cardiovascular disease risk.
- Negative coefficients for some interactions suggest complex relationships where certain exposure combinations may mitigate or modulate risk.
- The model’s use of nonlinear and interaction features confirms the multifaceted and nonlinear determinants underlying cardiovascular disease rates.

### Random Forest Regression Model

- A Random Forest regression model was built using the same features, leveraging its ability to capture complex nonlinear relationships and interactions without explicit feature engineering.
- Performance metrics:
  - Test RMSE: 3.112  
  - Test R²: 0.61, explaining 61% of the variance in cardiovascular disease rates.
- This model significantly outperformed the polynomial Ridge model, demonstrating better predictive accuracy and explanatory power.
- The results indicate that cardiovascular disease prevalence is influenced by complex and nonlinear combinations of environmental and socioeconomic factors.
- Important features identified include **Education, Poverty, Ozone, Unemployment, PM2.5, Toxic Releases,** and **Drinking Water Quality**.

---

## Important Findings

- Both models highlight **education and poverty** as critical social determinants of cardiovascular health.
- Environmental pollutants such as **PM2.5 and ozone** also play a substantial role.
- The Random Forest model’s superior performance suggests the relationships between these factors and cardiovascular disease are highly nonlinear and interactive.
- These insights support targeted public health strategies focusing on pollution reduction and social support in vulnerable communities.
  
---

## Next Steps and Recommendations

- Further refine models by incorporating additional environmental and health data or improving spatial resolution.
- Explore advanced ensemble methods like gradient boosting (e.g., XGBoost) for potentially improved predictions.
- Collaborate with public health officials to apply findings in designing interventions addressing both social determinants and environmental risks.
- Investigate temporal trends through longitudinal data to better understand causality and impact over time.

---

## Repository Structure

Capstone-CVD-analysis/
│
├── data/
│ └── CalEnviroScreen_4.0_data.csv # Raw dataset
│
├── doc/
│ └── Summary.docx # Project summary document
│ └── Summary_Capstone_1.docx # Capstone 1 summary document
│ └── Summary_Capstone_2.docx # Capstone 1 summary document
│
├── notebooks/
│ └── eda_cvd_analysis-2.ipynb # EDA, visualization, and modeling notebook
│
└── README.md # Project overview

## Instructions

1. Clone this repository:
    ```bash
    git clone https://github.com/deepak161087/Capstone-CVD-analysis.git
    ```
2. Open `Capstone_CVD_Analysis.ipynb` in Jupyter Notebook or VS Code.
3. Run the notebook to explore EDA, visualizations, and model results.
