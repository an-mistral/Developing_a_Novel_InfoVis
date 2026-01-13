# Developing a Novel Information Visualisation
For this project, I prepared a dataset of Formula 1 race data spanning from 1950 to 2017. The data was sourced from an open Kaggle repository, which compiles official historical records into structured CSV tables. While standard standings and championship summaries are widely available through the FIA and media outlets, my goal was to uncover fresh perspectives —novel statistics, trends, and comparisonsthat go beyond conventional podium results.While the Fédéra- tion Internationale de lAutomobile (FIA) and media outlets frequently publish standard stand- ings and championship tables, my goal was to surface fresh perspectives —novel statistics and crosscomparisonsthat go beyond the usual podium finishes. I processed and combined multiple tables (races, results, lap times, standings, constructors, drivers, and status codes) in Python, then crafted a series of focused Vega-Lite charts to reveal patterns.


This repository contains an end-to-end information visualisation project built on historical Formula 1 data (1950–2017). The goal is to go beyond standard standings and podium summaries by engineering analysis-ready tables from relational racing records and presenting *novel* perspectives through a multi-view **Vega-Lite** dashboard.

The project demonstrates practical skills in:
- Data wrangling and feature engineering on multi-table sports data (joins, aggregation, derived metrics)
- Reproducible analysis in Jupyter/Python
- Interactive visual analytics design and implementation (Vega-Lite specification)

---

## Project Overview

**Dataset:** Formula 1 race history (1950–2017) packaged as normalized CSV tables (races, results, lap times, standings, constructors/drivers metadata, status codes, etc.).  
**Outcome:** A set of curated, purpose-built views that reveal patterns in:
- Constructor dominance over decades
- Nationality distribution of career wins
- Non-finish failure modes (status codes)
- Competitive balance shifts (constructor points by season)
- Qualifying importance (win-rate by starting position)
- Pace vs championship points across scoring eras
- Fastest-lap vs winner’s best-lap comparisons across Grands Prix

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
