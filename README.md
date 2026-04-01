# GDP and Housing Affordability: A 61-Year Descriptive Analysis

## Overview

In 1962, Simon Kuznets — the economist credited with developing GDP — wrote (New Republic, 1962): "Distinctions must be kept in mind between quantity and quality of growth, between its costs and return, and between the short and the long term. Goals for more growth should specify more growth of what and for what." He was cautioning against exactly what has since occurred: GDP becoming the default measure of economic health and, by extension, human welfare.

This analysis tests one concrete dimension of that claim. Using quarterly U.S. data from 1963 through 2024, it examines whether GDP growth — the dominant signal of economic health in policy discourse — correlates with improved housing affordability for typical American households. Housing affordability is measured using the Median Multiple, the ratio of median home price to median household income, and serves as a proxy for middle-class economic stability.

The findings are striking: over six decades of nearly uninterrupted GDP growth, housing affordability moved in the opposite direction.

## Key Findings

- Real GDP and the Median Multiple are strongly positively correlated (r=0.799, R²=0.640, n=245)
- Housing was never truly affordable by Demographia standards during the full study period — the 1963 baseline Median Multiple of 3.38 already indicated moderate unaffordability
- Peak unaffordability was reached in Q4 2021 (MM=4.71), during a period of robust GDP growth
- By 2024 Q1 the Median Multiple remained elevated at 3.97, well above the affordable threshold of 3.0
- The most affordable period in the dataset was Q4 1970 (MM=2.66), opening questions about the conditions that produced it

## Methodology

Both the Median Multiple components — median home price and median household income — are expressed in real 2023 dollars. Nominal home prices (MSPUS) were deflated using the CPI-U annual average following the Federal Reserve Bank of Dallas methodology. Median family income (MEFAINUSA672N) is reported by FRED in real 2023 dollars and required no transformation. The Median Multiple is calculated following Demographia International Housing Affordability same-year methodology: median home price divided by median household income for the same period.

OLS regression in this case functions as descriptive of a trend of two series moving together rather than inferential. Both GDP and the Median Multiple are non-stationary series — standard OLS on non-stationary data can produce spurious results. The Durbin-Watson statistic of 0.310 confirms strong autocorrelation in the residuals, consistent with this interpretation. A companion cointegration analysis (Piece 2) is planned to address stationarity formally.

## Data Sources

| Series | Source | Frequency | Coverage |
|--------|--------|-----------|----------|
| Median Home Price (MSPUS) | FRED | Quarterly | 1963–2024 |
| CPI-U (CPIAUCSL) | FRED | Monthly | 1947–2024 |
| Real Median Family Income (MEFAINUSA672N) | FRED | Annual | 1953–2024 |
| Real GDP (GDPC1) | FRED | Quarterly | 1947–2024 |

## Limitations and Next Steps

This analysis is explicitly descriptive. The strong correlation between GDP and the Median Multiple reflects two trending series and should not be interpreted as causal. A planned companion analysis (Piece 2) will apply Augmented Dickey-Fuller testing and Engle-Granger cointegration analysis to assess whether a long-run equilibrium relationship exists between GDP and housing affordability.

## How to Reproduce

Clone the repository and ensure all dependencies are installed. Run the notebook top to bottom using **Kernel → Restart & Run All**. All data files are included in the `data/` folder with links to original FRED sources in the notebook.

**Required libraries:** pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn