# Company Financial Analysis in R

An R-based statistical modelling project examining relationships among company-level financial variables such as sales, market value, assets, profits and number of employees.

## Project overview

The analysis covers data inspection, missing-value checks, exploratory analysis, linear modelling, log transformations, diagnostics and model comparison. It also includes stepwise regression using `glmStepAIC`.

## Repository contents

- [`TASKS.Rmd`](TASKS.Rmd) — complete R Markdown analysis.

## Methods and tools

The project uses R packages including:

- `dplyr`
- `car`
- `ggplot2`
- `GGally`
- `caret`

The workflow includes:

- data-type and missing-value inspection,
- exploratory pair plots,
- linear regression,
- log-transformed regression,
- model diagnostics,
- multivariable modelling,
- stepwise model selection.

## Data requirements

The source analysis expects a local file named `companies.txt`. That dataset is not currently included in this repository, so the original data file is required to reproduce the full workflow.

## Reproducing the analysis

1. Place `companies.txt` in the R working directory.
2. Open `TASKS.Rmd` in RStudio.
3. Install any missing packages listed in the document.
4. Run or knit the analysis.

## Scope

This repository is maintained as a portfolio example of applied regression, model diagnostics and statistical programming in R.
