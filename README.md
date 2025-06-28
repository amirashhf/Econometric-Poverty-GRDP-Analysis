# 📈 Econometric Modeling of Poverty and Economic Growth

![Econometrics](https://img.shields.io/badge/Econometrics-003366?style=for-the-badge)
![TSLS](https://img.shields.io/badge/Method-2SLS-blue)
![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)

## 📖 Overview
Poverty and economic growth (measured by Gross Regional Domestic Product - GRDP) have a complex, bidirectional relationship. High poverty can impede economic growth, while slow growth can exacerbate poverty. This project aims to analyze this intricate relationship by replicating an econometric study on the socio-economic data of 35 regencies/cities in **Central Java, Indonesia, for the year 2022**. A **Simultaneous Equation Model (SEM)** is employed to untangle the factors that influence both poverty and GRDP concurrently.

## 📊 Dataset
* **Source:** Official data from **BPS (Statistics Indonesia) of Central Java Province** for the year 2022.
* **Scope:** 35 regencies/cities in Central Java.
* **Endogenous Variables:**
    * `Poverty Rate` (%)
    * `GRDP Growth` (%)
* **Exogenous Variables:**
    * `Population Growth` (%)
    * `Education Completion Rate` (%)
    * `Open Unemployment Rate` (%)
    * `Access to Clean Water` (%)

## ⚙️ Methodology: Simultaneous Equations
The core of this analysis is a two-equation simultaneous model designed to capture the feedback loop between poverty and economic growth.

#### The Model
1.  **Poverty Equation:**
    $Poverty = f(GRDP, Unemployment, Education, CleanWaterAccess)$
2.  **GRDP Equation:**
    $GRDP = f(Poverty, Education, PopulationGrowth, Unemployment)$

#### The Endogeneity Problem
Because `Poverty` is a predictor in the GRDP equation and `GRDP` is a predictor in the Poverty equation, a simultaneity bias (endogeneity) arises. Standard OLS regression would produce biased and inconsistent estimates.

#### The Solution: Two-Stage Least Squares (TSLS)
To address endogeneity, the model is estimated using the **Two-Stage Least Squares (TSLS)** method. This technique uses instrumental variables to isolate the exogenous variation in the endogenous predictors, allowing for unbiased estimation of the coefficients.

## 🔑 Key Findings from the Replication
The TSLS estimation yielded several key insights into the socio-economic dynamics of Central Java:

* **Impact on Poverty:** The only statistically significant factor affecting the **Poverty Rate** was **Access to Clean Water**, which had a strong negative coefficient (-0.432). This implies that a 1% increase in access to clean water is associated with a decrease in the poverty rate by 0.43 percentage points.
* **Impact on GRDP Growth:** The only statistically significant factor affecting **GRDP Growth** was **Population Growth**, with a negative coefficient (-0.950). This suggests that higher population growth puts downward pressure on per-capita economic growth in the region.
* **No Significant Simultaneous Effect:** A crucial finding from the model is the **lack of a statistically significant simultaneous relationship** between the Poverty Rate and GRDP Growth in Central Java for the year 2022. Neither variable proved to be a significant predictor for the other in their respective equations.

> **Conclusion:** While poverty and economic growth did not directly influence each other within this model's framework, the analysis successfully identified other key levers for policy: improving **basic infrastructure (clean water)** is key to poverty alleviation, while **managing population growth** is critical for economic acceleration.

## 📝 Replication Note
This project is an implementation and replication of the econometric model and analysis presented in the study:
> Qumayroh, N. P., et al. (2024). *MODEL PERSAMAAN SIMULTAN PADA ANALISIS HUBUNGAN KEMISIKINAN DAN PDRB PADA PROVINSI JAWA TENGAH TAHUN 2022*. JEBI: Jurnal Ekonomi Dan Bisnis.
