# Developing a Novel Information Visualisation
## Project Overview
This repository contains an end-to-end information visualisation project built on historical Formula 1 data (1950–2017). While the Fédération Internationale de l'Automobile (FIA) and media outlets frequently publish standard standings and championship tables, my goal was to surface fresh perspectives — novel statistics and cross-comparisons that go beyond the usual podium finishes. I processed and combined multiple tables (races, results, lap times, standings, constructors, drivers, and status codes) in Python, then crafted a series of focused **Vega-Lite** charts to reveal patterns.

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
   Loading the relevant Formula 1 CSV tables.
2. **Preprocessing & feature engineering**
   Merge related datasets by their keys and perform data cleaning and transformations. Apply chart-specific filtering (e.g., selecting winners, restricting season ranges, isolating non-finish statuses), convert time fields to standard units, group and aggregate data to compute summary statistics such as counts, averages, and totals, and derive additional analytical metrics. The processed data frames are saved as CSV or JSON files where appropriate.
3. **Export visualisation-ready datasets** to the `Visualisations_data/` directory.
4. **Vega-Lite v6 specification authoring**
   Implement all visualisations declaratively in a single Vega-Lite v6 JSON specification. Each chart is defined as an independent view with explicit data bindings, in-spec transformations, and visual encodings (position, colour, scale, tooltip), using appropriate marks (bar, rect, line, point, image).
5. **Dashboard composition**
   Combine individual views into a unified dashboard using `hconcat` and `vconcat`, applying consistent layout, scales, and interaction patterns across charts, and including a central image panel to improve visual perception and narrative coherence.
6. **Rendering & exploration**
    Render the final dashboard in any Vega-Lite–compatible environment (e.g., Vega Editor, Vega-Embed, Observable, or a static web page), enabling interactive exploration via tooltips and coordinated visual structure.

---
## Visualisation Highlights
The final dashboard presents all visualisations together in a single interactive view, with a central F1-themed image to provide better perspective and focus. Each visualisation in the dashboard conveys a specific insight:
- **Constructor Champions by Season (1958−2017)** – Image grid: Shows at a glance (through logos) which constructors dominated each period (e.g., Ferrari in the 2000s, McLaren in the 1980s, Red Bull in the early 2010s, Mercedes mid-2010s) and highlights one-off champions.
- **Top 20 Nationalities by Career Wins** – Bar chart: Reveals that British and German drivers have by far the most wins, with other countries (e.g., Brazil) also prominent, reflecting the sport’s regional concentration.
- **Top 20 Non-Finish Statuses** – Bar chart: Indicates the most common non-finish reason is being lapped (+1 Lap), followed by mechanical failures and accidents, highlighting reliability issues.
- **Constructor Points by Season (2010−2017)** – Heatmap: Highlights the shift in team dominance from Red Bull (2010–2013) to Mercedes (2014–2017) via higher point totals, while showing that Ferrari and McLaren remained consistently competitive.
- **Fastest Lap vs Winners Best Lap (2013−2017)** – Dual-line chart: Shows that on some circuits (e.g., Abu Dhabi, Spain) the race winner did not set the fastest lap (due to strategic tyre management), whereas on others (Britain, Brazil, Australia) the winner usually did, underscoring how track and strategy influence lap times.
- **Win Rate by Starting Position** – Stacked bar chart: Reveals roughly 77% of race wins come from the top three grid positions (emphasising qualifying importance), and that wins from starting 10th or lower are extremely rare.
- **Average Lap Time vs Season Points per Driver (1996−2017)** – Scatterplot: Indicates a strong correlation between faster average lap times and higher points, while the colour-coded eras show how scoring rule changes shifted performance clusters over seasons.

---
## How to Run

1. **Prepare the data**  
   Open `IVzpreprocessing.ipynb` in any environment that supports Jupyter notebooks (e.g., Jupyter Notebook, JupyterLab, VS Code). Run all cells to load the raw Formula 1 CSV files and generate the derived, chart-ready datasets in the `Visualisations_data/` directory.

2. **Render the dashboard**  
   Open the Vega-Lite specification `visualization.vl.json` in a Vega-Lite v6–compatible environment (e.g., the online Vega Editor, Vega-Embed, Observable, or a static HTML page). The specification loads the prepared datasets via URLs and renders the full interactive dashboard.

No additional configuration or backend services are required.

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


