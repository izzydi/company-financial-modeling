# Company Financial Modeling

An R-based statistical-modelling project examining relationships among company-level sales, market value, assets, profits and employment.

## Primary workflow

[`company_financial_analysis.Rmd`](company_financial_analysis.Rmd) is the audited source. It uses stable transformations, comparable response scales within model comparisons, an appropriate Gamma GLM for positive continuous market value and a leakage-aware profitability classification exercise.

## Repository structure

- [`company_financial_analysis.Rmd`](company_financial_analysis.Rmd) — audited R Markdown workflow.
- [`archive/legacy_course_analysis.Rmd`](archive/legacy_course_analysis.Rmd) — original coursework retained for provenance.
- [`data/README.md`](data/README.md) — expected data schema.
- [`R-packages.txt`](R-packages.txt) — version-pinned direct R dependencies.
- [`.github/workflows/r-ci.yml`](.github/workflows/r-ci.yml) — R 4.6.1 dependency and syntax CI.

## Audit improvements

The legacy analysis contained several methodological/technical issues that have been removed from the primary workflow: RMSE values from raw- and log-response models were compared directly, `sign(x) * log(abs(x))` was undefined when profit equalled zero, a Poisson count GLM was applied to continuous monetary market value, and one prediction used transformed inputs for a model trained on raw inputs.

The current workflow uses `sign(x) * log1p(abs(x))`, keeps regression comparisons on consistent scales, models positive market value with a Gamma log-link and deliberately removes `Profits` when predicting the derived `Profitable` outcome.

For the profitability comparison, Logistic Regression and KNN now use the **same complete-case classification sample** before the split. This removes the previous inconsistency where KNN performed median imputation while Logistic Regression could operate on a different effective set of rows. KNN still receives centering/scaling inside resampling because it is distance-based.

## Reproducibility and CI

Direct R package versions are pinned in [`R-packages.txt`](R-packages.txt). GitHub Actions uses R 4.6.1 and `pak` to install those exact direct package versions, then extracts and parses the canonical R Markdown source on every push and pull request.

`R-packages.txt` is a direct-dependency manifest rather than a complete `renv.lock` snapshot.

## Data

The original dataset is not committed. Place `companies.txt` under `data/` as described in [`data/README.md`](data/README.md).

## Reproducing the analysis

1. Install R 4.6.1.
2. Add the original dataset under `data/`.
3. Install `pak` and the pinned direct dependencies:

```r
install.packages("pak")
pak::pkg_install(readLines("R-packages.txt"), upgrade = FALSE)
```

4. Run or knit `company_financial_analysis.Rmd` from top to bottom.

## Scope

This is an academic modelling portfolio project. Its outputs are not investment advice or company valuation guidance.
