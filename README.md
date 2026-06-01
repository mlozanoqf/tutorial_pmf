# Financial modeling with R

This repository contains the source files for **Financial modeling with R**, a Quarto book by Dr. Martin Lozano. The book presents reproducible R workflows for financial data, prices and returns, trading rules, asset pricing, portfolio allocation, Value at Risk, and blockchain as a special financial application.

Published site: <https://mlozanoqf.github.io/tutorial_pmf/>

## Scope

The current version focuses on:

- Financial data extraction and visualization
- Price series, returns, cumulative returns, and return distributions
- Applied trading rules with technical indicators and a robo trader workflow
- Asset pricing with single-index and portfolio examples
- Asset allocation, diversification, rebalancing, and portfolio evaluation
- Market risk measurement with Value at Risk
- Blockchain foundations for blocks, hashes, proof-of-work, transactions, signatures, and network examples

## Book Structure

- `index.qmd`: preface, edition metadata, and publication metadata
- `01-introduction.qmd`: introduction to finance and R
- `02-financial-data.qmd`: financial data and technical analysis
- `03-prices-and-returns.qmd`: prices, returns, cumulative returns, and distributions
- `04-robotrader-in-r.qmd`: robo trader workflow in R
- `05-asset-pricing.qmd`: asset pricing and return models
- `06-asset-allocation.qmd`: portfolio allocation and rebalancing
- `07-value-at-risk.qmd`: Value at Risk and portfolio risk scenarios
- `08-blockchain.qmd`: blockchain mechanics in R
- `09-conclusion.qmd`: conclusion
- `references.qmd`: references

The chapter order is controlled by `_quarto.yml`.

## Repository Layout

- `_quarto.yml`: Quarto book configuration, HTML format settings, and chapter order
- `_freeze/`: cached execution results used by Quarto's `freeze: auto`
- `_book/`: generated HTML output created by `quarto render`
- `.github/workflows/publish.yml`: GitHub Actions workflow for rendering and deploying to GitHub Pages
- `R/book-edition.R`: helper functions for book edition and publication metadata
- `styles.css` and `*.html` partials: custom navigation, layout, analytics, and page behavior
- `references.bib`: bibliography
- `dataR.txt`: data used by the Value at Risk chapter
- Legacy `.Rmd`, `.pdf`, and related files: earlier source/history material kept in the repository

## Render Locally

Install Quarto and R, then render the book from the repository root:

```bash
quarto render
```

For interactive local preview:

```bash
quarto preview
```

To render one chapter while editing:

```bash
quarto render 07-value-at-risk.qmd --to html
```

The GitHub Actions workflow installs the R packages needed for deployment. For local rendering, use the package list in `.github/workflows/publish.yml`: `digest`, `dplyr`, `ggplot2`, `kableExtra`, `knitr`, `lubridate`, `MASS`, `openssl`, `PortfolioAnalytics`, `quantmod`, `randomForest`, `rmarkdown`, `ROI`, `ROI.plugin.glpk`, `ROI.plugin.quadprog`, `scales`, `tibble`, `tbl2xts`, `tidyquant`, `tidyr`, `vembedr`, and `xfun`.

## Publication

Pushing to `main` triggers the GitHub Actions workflow. The workflow installs Quarto and R on `windows-2022`, installs the required R packages, runs `quarto render`, uploads `_book`, and deploys the site to GitHub Pages.

## Maintenance Notes

- Edit the `.qmd` files and keep `_quarto.yml` aligned with the intended chapter order.
- Treat `_book/` and `.quarto/` as generated output.
- Because `freeze: auto` is enabled, Quarto reuses cached execution results when source chunks have not changed.
- After adding, removing, or renaming chapters, check `_quarto.yml`, `sidebar-chapter-sections.html`, `_freeze/`, and the rendered `_book/` output for stale references.
- Keep `sidebar-chapter-sections.html` aligned with chapters that need expanded sidebar subsections.
- Update `.github/workflows/publish.yml` when a chapter introduces a new R package required during deployment.

## License

This project is licensed under the GNU General Public License v3.0. See `LICENCE`.
