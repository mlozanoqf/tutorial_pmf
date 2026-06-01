# Financial modeling with R

This repository contains the Quarto book source for the Financial modeling with
R material.

Render locally with:

```bash
quarto render
```

The rendered site is generated in `_book/` and published through GitHub Actions.
The project uses `execute.freeze: auto`, so global renders reuse frozen
computations when the source file has not changed. Render a specific chapter
when you intentionally want to execute its code while editing:

```bash
quarto render 04-asset-pricing.qmd
```
