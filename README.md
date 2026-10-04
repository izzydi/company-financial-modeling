# Company Financial Modeling

An R-based statistical-modelling project examining relationships among company-level sales, market value, assets, profits and employment.

## Primary workflow

[`company_financial_analysis.Rmd`](company_financial_analysis.Rmd) is the audited source. It uses stable transformations, comparable response scales within model comparisons, an appropriate Gamma GLM for positive continuous market value and a leakage-aware profitability classification exercise.

## Repository structure

- [`company_financial_analysis.Rmd`](company_financial_analysis.Rmd) — audited R Markdown workflow.
- [`archive/legacy_course_analysis.Rmd`](archive/legacy_course_analysis.Rmd) — original coursework retained for provenance.
- [`data/README.md`](data/README.md) — expected data schema.
- [`R-packages.txt`](R-packages.txt) — direct package dependencies.

## Audit improvements

The legacy analysis contained several methodological/technical issues that have been removed from the primary workflow: RMSE values from raw- and log-response models were compared directly, `sign(x) * log(abs(x))` was undefined when profit equalled zero, a Poisson count GLM was applied to continuous monetary market value, and one prediction used transformed inputs for a model trained on raw inputs.

The current workflow uses `sign(x) * log1p(abs(x))`, keeps regression comparisons on consistent scales, models positive market value with a Gamma log-link and deliberately removes `Profits` when predicting the derived `Profitable` outcome.

## Data

The original dataset is not committed. Place `companies.txt` under `data/` as described in [`data/README.md`](data/README.md).

## Reproducing the analysis

1. Add the original dataset under `data/`.
2. Install packages listed in [`R-packages.txt`](R-packages.txt).
3. Run or knit `company_financial_analysis.Rmd` from top to bottom.

## Scope

This is an academic modelling portfolio project. Its outputs are not investment advice or company valuation guidance.
