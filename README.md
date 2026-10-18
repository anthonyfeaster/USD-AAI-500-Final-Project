# Predicting NFL Third Down Conversions

**Project Status: Active**

## Project Overview

This project is part of the AAI-500 course in the Applied Artificial
Intelligence Program at the University of San Diego. Team 2 analyzes
NFLverse play-by-play data to identify factors associated with successful
third-down conversions and develop a predictive model. The analysis aims
to improve understanding of third-down situations and inform discussion
of offensive play selection.

**Research question:** Which game situations are associated with successful
NFL third-down conversions, and how accurately can conversion outcomes
be predicted?

## Team Members

- [Anthony Feaster II](https://github.com/anthonyfeaster)
- [Nathan Sabbara](https://github.com/sabbanat)

## Data Source and Documentation

This project uses NFLverse play-by-play data from the 2023–2026 seasons.
The CSV files are stored in `data/raw/` so all team members analyze the
same data. The 2026 file contains partial-season data. The notebook reads
these saved files rather than downloading updates automatically.

The combined dataset contains **156,084 records and 372 columns**. After
filtering, the analysis dataset contains **21,948 plays and 16 selected
variables**.

- [NFLverse Play-by-Play Data](https://github.com/nflverse/nflverse-data/releases/tag/pbp)
- [Official Play-by-Play Data Dictionary](https://nflreadr.nflverse.com/articles/dictionary_pbp.html)
- [nflfastR Field Descriptions](https://nflfastr.com/articles/field_descriptions.html)

The documentation defines the original dataset variables. Project-specific
groupings, such as yards to go, field position, and score situation, are
defined in the exploratory data analysis notebook.

## Analysis Approach

The exploratory analysis focuses on regular-season third down run and
pass plays with a recorded conversion outcome.

The target variable is `third_down_converted`:

- 0: Unsuccessful conversion
- 1: Successful conversion

`notebooks/model.ipynb` compares a linear model, an identity-link binomial
model, and a logistic regression, then estimates the logistic model.
Scrambles are coded as passes. The fit uses the 2023–2025 regular season
and holds out the partial 2026 season.

## Methods Used

- Data cleaning and preparation
- Descriptive statistics
- Exploratory data analysis
- Data visualization
- Logistic regression for a binary conversion outcome

## Technologies

- Python
- pandas and NumPy
- Matplotlib and Seaborn
- Jupyter Notebook
- Git and GitHub

## Repository Structure

- `data/`: Project datasets.
- `notebooks/01_initial_eda.ipynb`: Data preparation, exploratory analysis,
  summary tables, and visualizations.
- `notebooks/model.ipynb`: Comparison of three binary models and the
  estimated logistic regression.
- `notebooks/appendix.ipynb`: The exploratory notebook followed by the
  logistic model, with one result per cell.
- `report_figures/`: Equation and fitted-curve figures for the report.
- `requirements.txt`: Packages used by the model notebook.
- `README.md`: Project overview and documentation.

## Installation and Usage

Clone the repository and enter the project directory:

```bash
git clone https://github.com/anthonyfeaster/USD-AAI-500-Final-Project.git
cd USD-AAI-500-Final-Project
```

The four `play_by_play_2023.csv` through `play_by_play_2026.csv` files
must be present in `data/raw/`.

The notebook currently uses Python 3.13. To run the project on your
computer, create and activate a virtual environment from the repository
root (macOS/Linux):

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the required Python packages:

```bash
python -m pip install pandas numpy matplotlib seaborn ipykernel jupyterlab
python -m pip install -r requirements.txt
```

`requirements.txt` adds the packages used by `notebooks/model.ipynb`
(SciPy and statsmodels).

Open `notebooks/01_initial_eda.ipynb`, `notebooks/model.ipynb`, or
`notebooks/appendix.ipynb` in your preferred notebook environment
and select a Python kernel with the required packages installed.

Restart the kernel and run all cells from top to bottom. Run the notebook
from the repository root or the `notebooks/` directory; the loading cell
supports both locations. Data loading uses the local files in `data/raw/`.
Results stay consistent while these CSV files remain unchanged.

## Key Findings

These findings are preliminary and describe the filtered analysis dataset:

- Third-down attempts were successful **39.69%** of the time.
- Conversion rates decreased as yards to go increased: **63.38%** for
  1–2 yards compared with **15.07%** for 11 or more yards.
- Runs had a higher overall conversion rate (**53.34%**) than passes
  (**35.14%**). This comparison does not establish that running causes
  greater success; play selection may reflect differences in distance
  and other game situations.

## Limitations

- The fixed snapshot contains an incomplete 2026 season, so comparisons across seasons should
  account for differences in coverage.
- Exploratory relationships describe associations and do not establish
  causation.


## References

Agresti, A., & Kateri, M. (2022). *Foundations of statistics for data scientists:
With R and Python*. CRC Press. https://doi.org/10.1201/9781003159834
