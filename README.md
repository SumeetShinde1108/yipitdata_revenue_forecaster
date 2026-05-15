# Memo: Walmart Revenue Forecasting Using Retail Sales Data

## Objective

This analysis evaluated whether monthly U.S. retail sales data from FRED could improve prediction of Walmart’s quarterly revenue relative to a simple naive baseline.

## Approach

The retail sales data was aggregated from monthly to quarterly frequency and aligned with Walmart’s quarterly revenue using common quarterly periods. To reduce long-term trend effects and seasonality, year-over-year (YoY) growth rates were calculated for both datasets.

Three forecasting approaches were evaluated:

1. Naive persistence baseline  
2. Retail-sales regression model  
3. Lagged retail-sales regression model  

Evaluation was performed using chronological train/test splitting to avoid look-ahead bias and preserve realistic forecasting conditions.

## Results

The naive baseline outperformed both retail-sales-based models.

| Model | MAE | RMSE |
|---|---|---|
| Naive Baseline | 0.0171 | 0.0237 |
| Retail Regression | 0.0298 | 0.0323 |
| Lagged Retail Regression | 0.0300 | 0.0325 |

The retail-sales-based models produced smoother predictions that failed to capture changes in Walmart revenue growth accurately.

## Interpretation

Although retail sales growth showed some visual relationship with Walmart revenue growth, the relationship was not strong enough to improve forecasting performance out-of-sample.

This likely reflects several factors:

- Walmart revenue already contains strong persistence and seasonality
- Broader retail sales data may be too noisy or insufficiently Walmart-specific
- The COVID period introduced structural distortions in consumer behavior and spending patterns

The lagged retail-sales model also failed to improve performance, suggesting limited predictive value from retail sales alone.

## Conclusion

Based on this analysis, retail sales data from FRED did not predict Walmart quarterly revenue better than a naive persistence baseline.

The results suggest that Walmart’s own historical revenue dynamics remain a stronger forecasting signal than broader retail sales indicators in this setup.
