# Steven Mou's Website

This repo contains my personal Quarto website and the computational blog posts that I've written. One computational post is written in R and one computational post is written in Python

The website is built with Quarto. Reproducible environments are managed with:
- 'renv' for R
- 'uv' for Python


## Installation Requirements

- Quarto 1.10.18
- uv 0.12.7
- R 4.6.1

The R environment is managed with `renv`, and the Python environment is managed with `uv`.
- renv is used to restore the R package environment and bootstraps itself from the project files
- Python environment is restored from pyproject.toml and uv.lock using uv
The rendered website is written to the docs/directory for Github pages. 

## Build Instructions

1. Clone the repo:
```{bash}
git clone https://github.com/Stevenm19/stevenm19.github.io.git
cd stevenm19.github.io
```

2. Restore the Python Environment
```{bash}
uv sync
```

3. Restore the Python Environment
Start a new R session from the top level of the repo and run the following
```{r}
renv::restore()
```
Then, exit R.

4. Render the website
From the top level of the repo, run:
```{bash}
uv run quarto render
```
The rendered site will be written to docs/

### Preview the website localy
```{bash}
uv run quarto preview
```

## Data
Each computation blog post documents its own data source, data link and licensing information directly in the post. 

The current posts use locally stored datasets, so the site does not need to download those datasets from the internet during rendering. 
- Both datasets are retrieved from Kaggle
