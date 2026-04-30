# DS 3000 — Stock Prices & ESG Score Analysis

## Course context

DS 3000 — Foundations of Data Science · Khoury College of Computer Sciences, Northeastern University · Fall 2024.

## Project overview

Group project investigating whether ESG (Environmental, Social, Governance) ratings predict stock performance for the top 100 S&P 500 companies, using polynomial regression and PCA-based K-Means clustering on Yahoo Finance data. Finding: ESG alone is a weak signal for stock price (negative R²) and market cap, but PE Ratio is the most ESG-responsive metric — a polynomial model with an Environmental × Social interaction term reaches R² ≈ 0.14 under LOO-CV, the only target where ESG features generalize beyond the training sample.

- "All models are wrong, but some are useful." — George Box


## Repository contents

### Notebooks (chronological order)

| File | Phase |
|---|---|
| `Python Style Guide.ipynb` | Course-provided Python style guide |
| `ProjectGuidelines.ipynb` | Course-provided project guidelines |
| `Project_Proposal_With_Dataframe.ipynb` | Initial individual proposal |
| `Project_Phase_II_Updated__1_ (1).ipynb` | Phase II — analysis |
| `Project_Phase_III.ipynb` | Phase III — refinement |
| `Final_Project.ipynb` | Final submission notebook |
| `ds3000_stock_esg_project.pdf` | Presentation on the project |

### Residual Diagnostics — PE Ratio Model
We checked residual plots to test whether our polynomial regression's error structure was random (a key linear-regression assumption). 

<img width="848" height="367" alt="Screenshot 2026-04-30 at 7 17 41 PM" src="https://github.com/user-attachments/assets/d8aff31b-818e-4bbc-9853-08b1d18493b5" />
Plot 1: Residual Plot vs. Social Risk — PE Ratio                                          
                                                                                            
  ▎ Residuals from the polynomial regression on PE Ratio, plotted against the Social Risk 
  ▎ subscore. Points scatter roughly evenly above and below zero across the full range of   
  ▎ Social Risk values, with no obvious trend or wedge shape — consistent with the 
  ▎ homoscedasticity assumption holding for this feature.    

<img width="445" height="617" alt="Screenshot 2026-04-30 at 7 18 16 PM" src="https://github.com/user-attachments/assets/eb5bf3d8-48ec-4b8b-9593-a2ebf3f04789" />
Residuals vs. Governance Risk subscore. The slight funnel shape (wider at low values) indicates mild heteroscedasticity - a limitation we flagged; standard transformations did  
not fully resolve it.

<img width="428" height="613" alt="Screenshot 2026-04-30 at 7 18 10 PM" src="https://github.com/user-attachments/assets/4dfbeb05-7d6a-4bc2-a449-7eee344a2135" />



<img width="419" height="317" alt="Screenshot 2026-04-30 at 7 18 18 PM" src="https://github.com/user-attachments/assets/79205294-e606-46bc-8f57-7e571c1d3773" />

## Tech stack

Python 3 · Jupyter · pandas · NumPy · matplotlib · seaborn

