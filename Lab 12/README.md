# Architecting the Prediction Engine

## Objective
Develop a multivariate Ordinary Least Squares (OLS) forecasting engine capable of estimating residential property values and quantifying predictive performance through explicit loss measurement in real monetary terms.

## Methodology
- **Data Ingestion:** Utilized the Zillow ZHVI 2026 Micro Dataset, a cross-sectional snapshot of contemporary housing market characteristics.  
- **Feature Specification:** Selected structural and locational housing attributes—including square footage, property age, proximity to transit, and school district rating—as explanatory variables.  
- **Model Architecture:** Implemented a multivariate OLS regression using Python’s scientific computing stack (**pandas**, **numpy**) and the **statsmodels Patsy Formula API** for clear econometric model specification.  
- **Parameter Estimation:** Estimated regression coefficients to quantify the marginal contribution of each housing attribute to property valuation.  
- **Prediction Pipeline:** Generated fitted values to transition from classical explanatory modeling toward a predictive framework.  
- **Performance Evaluation:** Calculated the **Root Mean Squared Error (RMSE)** between observed market values and model predictions to measure the model’s average financial prediction error in **US dollars**.

## Key Findings
This project demonstrates how a traditional econometric model can be operationalized as a predictive pricing engine. By translating statistical fit into a tangible financial metric—**RMSE in USD**—the model’s predictive uncertainty can be interpreted directly as **algorithmic business risk**.  

This framework bridges classical econometric interpretation with modern predictive analytics, allowing practitioners to assess how accurately the model approximates real estate valuations and the expected magnitude of pricing deviation when deploying the model in real-world decision environments.
