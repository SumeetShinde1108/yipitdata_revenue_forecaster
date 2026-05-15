# LLM Prompt Log & Reflection

## Example Prompts Used

### Prompt 1
Explain the assignment requirements and identify the key forecasting problem being tested.

### Prompt 2
Help structure a clean Jupyter notebook workflow for time-series forecasting analysis.

### Prompt 3
Explain how to correctly aggregate monthly retail sales data into quarterly frequency.

### Prompt 4
Help identify potential look-ahead bias and proper chronological train/test splitting for time-series evaluation.

### Prompt 5
Suggest baseline forecasting approaches appropriate for Walmart quarterly revenue prediction.

### Prompt 6
Help interpret why a retail-sales-based regression model underperformed a naive persistence baseline.

---

# Reflection

The LLM was most useful for structuring the workflow, explaining forecasting concepts, and helping debug implementation issues during preprocessing and evaluation. It accelerated notebook organization and clarified several time-series concepts such as quarter alignment, out-of-sample testing, and baseline construction.

One important issue occurred during quarterly aggregation. The suggested pandas syntax used `.resample("Q")`, which failed under the installed pandas version because the `"Q"` frequency alias is deprecated in favor of `"QE"`. This required manual debugging and correction after inspecting the error message. This highlighted the importance of validating AI-generated code rather than trusting outputs blindly.

The LLM also initially emphasized MAPE as an evaluation metric, but the metric became unstable because Walmart revenue growth occasionally approached zero. After inspecting the results, MAE and RMSE were treated as more reliable evaluation metrics for this analysis.

Overall, the LLM significantly improved development speed and conceptual understanding, but human judgment remained necessary for debugging, validating assumptions, and interpreting forecasting results appropriately.