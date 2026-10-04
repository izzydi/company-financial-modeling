# Company Financial Modeling

An R-based statistical modelling project examining relationships among company-level financial variables such as sales, market value, assets, profits and number of employees.

## Project overview

The analysis covers data inspection, missing-value checks, exploratory analysis, linear modelling, log transformations, diagnostics and model comparison. It also includes stepwise regression using `glmStepAIC`.

## Repository structure

- [`company_financial_analysis.Rmd`](company_financial_analysis.Rmd) — complete R Markdown analysis.
- [`.gitignore`](.gitignore) — excludes local R/RStudio artifacts.

## Methods and tools

The project uses R packages including `dplyr`, `car`, `ggplot2`, `GGally` and `caret`.

The workflow includes:

- data-type and missing-value inspection,
- exploratory pair plots,
- simple and multivariable linear regression,
- log-transformed regression,
- model diagnostics,
- model comparison and stepwise selection.

## Data requirements

The source analysis expects a local file named `companies.txt`. The dataset is not committed to this repository, so the original data file is required to reproduce the full workflow.

## Reproducing the analysis

1. Place `companies.txt` in the repository root.
2. Open `company_financial_analysis.Rmd` in RStudio.
3. Install any missing packages used by the document.
4. Run or knit the analysis.

## Scope

This repository is maintained as a portfolio example of applied regression, model diagnostics and statistical programming in R.
