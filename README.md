# Developing a Novel Information Visualisation
## Project Overview
This repository contains an end-to-end information visualisation project built on historical Formula 1 data (1950–2017). While the Fédération Internationale de lAutomobile (FIA) and media outlets frequently publish standard standings and championship tables, my goal was to surface fresh perspectives — novel statistics and cross-comparisons that go beyond the usual podium finishes. I processed and combined multiple tables (races, results, lap times, standings, constructors, drivers, and status codes) in Python, then crafted a series of focused **Vega-Lite** charts to reveal patterns.

The project demonstrates practical skills in:
- Data wrangling and feature engineering on multi-table sports data 
- Reproducible processing, analysis using Jupyter notebooks and Python (pandas)
- Interactive visual analytics design and implementation (Vega-Lite v6 specification)

---
## Data Description
The data was sourced from an open [Kaggle repository](https://www.kaggle.com/datasets/cjgdev/formula-1-race-data-19502017?resource=download%20) that compiles official Formula 1 historical records (1950–2017) into a structured set of normalised CSV tables. 

**`Formula1_data/`– Raw Data Tables:** Original CSV files as downloaded. Key tables used: 
- `races.csv` – Race metadata for each Grand Prix (raceId, year, name, date, etc.)
- `results.csv` – Detailed results for every driver in every race
- `lapTimes.csv` – Detailed lap-by-lap timings for each driver in each race
- `driverStandings.csv` & `constructorStandings.csv` – Championship standings (points totals) for each driver/team after every race
- `drivers.csv` & `constructors.csv` – Metadata for drivers and teams (name, nationality, etc.)
- `status.csv` – Definitions for status codes (e.g., reasons a car did not finish, like Accident, Engine, or +1 Lap)

**`Visualisations_data/`** – Processed Datasets: Curated data files derived from the raw tables via the preprocessing notebook. These CSV/JSON files contain aggregated or transformed data tailored for each visualisation, ready to be loaded by the Vega-Lite dashboard.

---
## Workflow pipeline

1. **Raw data ingestion** 
2. **Preprocessing & feature engineering** 
3. **Export visualization-ready datasets** 
4. **Vega-Lite v6 specification authoring** 
5. **Dashboard composition**
6. **Rendering & exploration** 

---
## Visualisation Highlights
The final dashboard presents all visualizations together in a single interactive view, with a central F1-themed image to provide better perspective and focus. Each visualization in the dashboard conveys a specific insight:
- Constructor Champions by Season (1958− 2017):
- Top 20 Nationalities by Career Wins:
- Top 20 Non-Finish Statuses:
- Constructor Points by Season (2010− 2017):
- Fastest Lap vs Winners Best Lap (2013− 2017):
- Win Rate by Starting Position:
- Average Lap Time vs Season Points per Driver (1996− 2017):
  
---
## How to Run
To reproduce the analysis and view the visualizations, follow these steps:
1. Run the preprocessing notebook: Open `IVzpreprocessing.ipynb` in Jupyter and run all cells. This will read the raw CSV files from `Formula1_data/` and regenerate all derived datasets in `Visualisations_data/`. (The notebook documents the data wrangling process and intermediate analysis.)
   
2. Open the Vega-Lite dashboard: Load the `visualization.vl.json` specification in a Vega-Lite compatible viewer. For example, you can copy the JSON content into the online Vega Editor (select the Vega-Lite mode). The interactive dashboard with all charts will render in the browser, allowing you to explore tooltips and interactions. No additional setup is required since the spec references the prepared data files directly.
   
---
## Deliverables
- Interactive dashboard specification: `visualization.vl.json` (Vega-Lite v6 JSON defining all charts and layout)
- Data preprocessing notebook: `IVzpreprocessing.ipynb` (Python code for data cleaning, integration, and feature engineering)
- Raw data files: `Formula1_data/` directory (original CSV files from Kaggle)
- Processed visualization data: `Visualisations_data/` directory (derived datasets ready for use in charts)
- Design documentation:
    - `IV_design.png` (overview diagram/image of the visual design)
    - `IV_design_report.pdf` (report design rationale)
- Team logo images: `images/` directory (PNG files of constructor logos used in the logo grid chart)

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


