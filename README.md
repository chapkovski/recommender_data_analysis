# Recommender Data Analysis

This folder contains Quarto reports and derived summary tables for exploratory analysis of pilot and raw recommender-study data.

## What is in this repository

- `pilot_raw_basic_analysis.qmd`: Quarto report for participant-level, decision-level, round-level, and treatment-level summaries based on files in `raw_data/`.
- `pilot_movie_left_right_ratings.qmd`: Quarto report summarizing left-right movie ratings based on files in `pilot_data/`.
- `pilot_raw_basic_analysis.html`: Rendered HTML output for the raw data report.
- `pilot_movie_left_right_ratings.html`: Rendered HTML output for the movie ratings report.
- `pilot_raw_decision_level.csv`, `pilot_raw_participant_level.csv`, `pilot_raw_round_summary.csv`, `pilot_raw_treatment_summary.csv`: Derived summary tables produced by the raw analysis report.
- `pilot_movie_left_right_summary.csv`: Derived summary table produced by the movie ratings report.
- `raw_data/`: Newer raw CSV exports used by the raw analysis report.
- `pilot_data/`: Pilot CSV exports used by the movie ratings report.

## Requirements

The analysis files are written in Quarto using R.

You will need:

- Quarto
- R
- The following R packages: `dplyr`, `tidyr`, `ggplot2`, `jsonlite`, `knitr`

## Reproducing the reports

Render the raw analysis report:

```bash
quarto render pilot_raw_basic_analysis.qmd
```

Render the movie ratings report:

```bash
quarto render pilot_movie_left_right_ratings.qmd
```

Each report automatically picks the latest matching CSV file in its input directory based on filename sorting.

## Data expectations

- `raw_data/` should contain files matching `main_*.csv`, `pre_experimental_*.csv`, and `PageTimes-*.csv`.
- `pilot_data/` should contain a file matching `main_*.csv`.

If required input files are missing, the Quarto render will stop with an error.

## GitHub notes

The repository is configured with:

- `.gitignore` for macOS, VS Code, Quarto cache files, Python cache files, R session files, and local virtual environments.
- `.gitattributes` to normalize text files across platforms.

At the moment, rendered HTML reports and CSV outputs are not ignored, so they can be versioned if you want GitHub to show the generated artifacts alongside source files.