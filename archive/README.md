# Legacy course analysis

`legacy_course_analysis.Rmd` preserves the original coursework.

The audited source is [`../company_financial_analysis.Rmd`](../company_financial_analysis.Rmd). The legacy workflow compared RMSE values measured on different response scales, used a signed log transform that is undefined at zero, applied a Poisson model to continuous monetary market value and mixed transformed predictors into a prediction for a model trained on raw predictors. Those issues are corrected in the audited workflow.
