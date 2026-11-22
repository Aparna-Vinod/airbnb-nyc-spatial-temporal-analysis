# Spatial and Temporal Analysis of Airbnb Rental Prices in New York City (2021-2026)

MSc Spatial Analytics capstone project. The study describes how Airbnb average daily rates vary across New York City neighbourhoods and over time, and tests whether high and low rates are geographically clustered (Global and Local Moran's I). It is observational: no causal claims are made.

## Research questions

1. How do Airbnb rental rates vary across NYC neighbourhoods?
2. How have rates changed over time?
3. Are there seasonal patterns?
4. Are high and low rates geographically clustered?
5. How have neighbourhood-level clusters changed between 2022 and 2025?

## Main findings

| Topic | Result |
|---|---|
| Spatial pattern | Highest neighbourhood medians in Manhattan; lowest in parts of the Bronx and Queens (2022: about $224-$307 versus $46-$62 per night for the top and bottom eight) |
| Trend (March 2021 - February 2026) | Citywide monthly median rose from $108.5 to $158.5, with a recurring dip around January |
| Seasonality (2022-2025) | January-April below an average month in all four years; June, July and September-December above |
| Yearly change 2022-2025 | +16.7% (all records); +10.5% for 711 listings present throughout; +6.2% for 1,392 listings with data in both years (nominal USD) |
| Global Moran's I | 0.685, 0.687, 0.650, 0.569 for 2022-2025 (p = 0.001, 999 permutations) |
| Local Moran's I (FDR 5%) | Seven Manhattan neighbourhoods High-High in all four years; Jackson Heights Low-Low in all four years |
| Robustness | Clustering held for thresholds of 3 and 10 listings, log rates and months with occupancy above 0; it weakened when only entire homes were analysed (Moran's I about 0.36) |

Caveats: the set of listings and of analysed neighbourhoods changes between years, so year-to-year differences are descriptive and not a like-for-like comparison; neighbourhood-level changes between 2022 and 2025 are not robust; rates are nominal USD.

## Data

The raw data are **not** stored in this repository. See [`data/README.md`](data/README.md) for sources, licences and download instructions.

- Airbnb data: *Airbnb Data: New York City 5Y (2021-26)*, Jason_AirROI (data sourced from AirROI), Kaggle, CC BY-NC 4.0. Used for non-commercial academic purposes with attribution.
- Boundaries: 2020 Neighborhood Tabulation Areas (NTAs), NYC Department of City Planning, via NYC Open Data.

## Method in brief

1. Verify and clean the data (every exclusion is logged in `outputs/tables/02_exclusion_log.csv`).
2. Assign listings to NTAs by point-in-polygon spatial join on coordinates.
3. Two-step neighbourhood medians: median per listing and year, then median per NTA; at least five listings per NTA and year.
4. Temporal analysis: monthly trend, seasonal index and yearly comparison, with fixed-listing robustness checks.
5. Queen contiguity weights (row-standardised), Global Moran's I and Local Moran's I (LISA), 999 permutations, Benjamini-Hochberg FDR at 5%.
6. Cluster comparison across 2022-2025, then sensitivity checks.

## Repository structure

```
notebooks/   01 data understanding, 02 data cleaning, 03 exploratory analysis,
             04 spatial price analysis, 05 temporal analysis, 06 spatial clustering,
             07 spatiotemporal comparison, 08 sensitivity checks, 09 QGIS export
outputs/
  figures/   charts from the notebooks
  tables/    result tables (CSV)
  qgis/      GeoPackage and QGIS project (neighbourhood-level results only)
maps/        map images (Python maps and the QGIS LISA maps)
report/      final report (LaTeX)
data/        data instructions only (raw and processed data are kept locally)
requirements.txt
```

## How to reproduce (Windows)

1. Clone the repository and open it in VS Code.
2. Create and activate a virtual environment, then install the packages:
   ```
   python -m venv .venv
   .venv\Scripts\Activate.ps1
   python -m pip install -r requirements.txt
   ```
3. Download the data as described in `data/README.md` and place the files in `data/raw/` (`listings.parquet`, `past_rates.csv`, `nta2020.geojson`).
4. Run the notebooks in numerical order (Restart and Run All in each).

Python 3.13.7 was used. If Windows Application Control blocks a compiled library, restart the kernel and run again.

## QGIS

Open `outputs/qgis/airbnb_nyc_results.qgz` in QGIS (project CRS EPSG:2263). The layers `nta_results`, `nta_all_context` and `boroughs` come from `airbnb_nyc_results.gpkg`, which notebook 09 exports. The LISA maps for 2022-2025 show the Global Moran's I of each year on the map.

## Limitations

- Listings in the data change over time, and many neighbourhoods have few listings (minimum five used).
- NTAs approximate neighbourhoods; some listing coordinates may be slightly inaccurate.
- Room-type mix differs between neighbourhoods and contributes to the clustering.
- Rates are nominal USD; the dataset does not define ADR for months with zero occupancy.

## Project by

Aparna V, MSc Computer Science with Data Analytics. 
