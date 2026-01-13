# Developing a Novel Information Visualisation
## Project Overview
This repository contains an end-to-end information visualisation project built on historical Formula 1 data (1950–2017). While the Fédération Internationale de lAutomobile (FIA) and media outlets frequently publish standard standings and championship tables, my goal was to surface fresh perspectives — novel statistics and cross-comparisons that go beyond the usual podium finishes. I processed and combined multiple tables (races, results, lap times, standings, constructors, drivers, and status codes) in Python, then crafted a series of focused **Vega-Lite** charts to reveal patterns.

The project demonstrates practical skills in:
- Data wrangling and feature engineering on multi-table sports data (joins, aggregation, derived metrics)
- Reproducible preprocessing, analysis in Jupyter/Python
- Interactive visual analytics design and implementation (Vega-Lite v6 specification)

---
## Data Description
The data was sourced from an open [Kaggle repository](https://www.kaggle.com/datasets/cjgdev/formula-1-race-data-19502017?resource=download%20) that compiles official Formula 1 historical records (1950–2017) into a structured set of normalized CSV tables.

**`Formula1_data/` (Raw relational tables)** 
This folder contains the original CSV tables. These files are treated as the canonical input layer: tables are linked via stable identifiers (e.g., raceId, driverId, constructorId, statusId) and are transformed in `IVzpreprocessing.ipynb` into the curated, visualization-ready datasets stored in `Visualisations_data/`.

Core tables used in this project:
- `races.csv`: race metadata (raceId, year, name, etc.)
- `results.csv`: race outcome records (positions, grid, fastest lap fields, statusId, constructorId/driverId keys, etc.)
- `lapTimes.csv`: per-lap timing observations
- `driverStandings.csv`, `constructorStandings.csv`: standings snapshots per race
- `drivers.csv`, `constructors.csv`: entity metadata
- `status.csv`: decoding table for non-finish / finish status codes

---
## Workflow pipeline



---
## Reproducing 


---
## Deliverables
- Interactive dashboard specification: `visualization.vl.json`
- Preprocessing & feature engineering notebook: `IVzpreprocessing.ipynb`
- Raw dataset tables: `Formula1_data/`
- Derived visualisation datasets: `Visualisations_data/`
- Design artefacts and write-up:
    - `IV_design.png` (design/overview image)
    - `IV_design_report.pdf` (full report and interpretation)
- Brand assets for the logo grid: `images/`
  
---
## Repository Structure

```text
Developing_a_Novel_InfoVis/
├── IV_design.png
├── IV_design_report.pdf
├── IVzpreprocessing.ipynb
├── visualization.vl.json
├── README.md
├── Formula1_data/
│   ├── circuits.csv
│   ├── constructorResults.csv
│   ├── constructorStandings.csv
│   ├── constructors.csv
│   ├── driverStandings.csv
│   ├── drivers.csv
│   ├── lapTimes.csv
│   ├── pitStops.csv
│   ├── qualifying.csv
│   ├── races.csv
│   ├── results.csv
│   ├── seasons.csv
│   └── status.csv
├── Visualisations_data/
│   ├── avgLapTime_vs_seasonPoints.csv
│   ├── champions_logos.csv
│   ├── constructor_points_by_year.csv
│   ├── gp_lap_compare_2010_2017.csv
│   ├── histogram_summary.json
│   └── wins_by_country.csv
└── images/
    ├── BRM.png
    ├── Brawn.png
    ├── Cooper.png
    ├── Matra.png
    ├── Repco.png
    ├── Vanwall.png
    ├── benetton.png
    ├── ferrari.png
    ├── image.png
    ├── lotus.png
    ├── mclaren.png
    ├── mercedes-benz.png
    ├── oracle_red_bull.png
    ├── renault.png
    ├── tyrrel.png
    └── williams.png


