# Predicting NFL Third Down Conversions

## Project Overview

USD AAI-500 Team 2 final project analyzing NFLverse play-by-play data
to identify factors associated with successful third down conversions
and develop a predictive model.

## Team Members

- [Anthony Feaster II](https://github.com/anthonyfeaster)
- [Nathan Sabbara](https://github.com/sabbanat)

## Data Source and Documentation

This project examines NFLverse play-by-play data from the 2023–2026
seasons. The 2026 season is incomplete at the time of this analysis.

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

Predictive modeling methods and evaluation procedures will be documented
as the project progresses.

## Repository Structure

- `data/`: Project datasets.
- `notebooks/01_initial_eda.ipynb`: Data preparation, exploratory analysis,
  summary tables, and visualizations.
- `README.md`: Project overview and documentation.

## Setup and Usage

The notebook currently uses Python 3.13. From the repository root, create
and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the required packages:

```bash
python -m pip install pandas numpy matplotlib seaborn pyarrow ipykernel jupyterlab
```

`pyarrow` enables pandas to read the Parquet data files.

Open `notebooks/01_initial_eda.ipynb` in VS Code and select the `.venv`
Python environment as the notebook kernel. Alternatively, run
`jupyter lab` from the activated environment and open the notebook there.

Restart the kernel and run all cells from top to bottom. Internet access
is required because the notebook downloads the data from NFLverse.
Counts and results may change as the ongoing 2026 season data is updated.

## Key Findings

Findings will be added...

## Limitations

- The 2026 season is incomplete, so comparisons across seasons should
  account for differences in coverage.
- Exploratory relationships describe associations and do not establish
  causation.


## References

Agresti, A., & Kateri, M. (2022). *Foundations of statistics for data scientists:
With R and Python*. CRC Press. https://doi.org/10.1201/9781003159834
