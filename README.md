# Spatial and Temporal Analysis of Airbnb Rental Prices in New York City (2021-2026)

## Project Overview
This project explores the spatial and temporal patterns of Airbnb rental prices across New York City using data from 2021 to 2026.
The project focuses on understanding how rental rates vary geographically across neighbourhoods, how they change over time, and whether areas with similar rental prices form statistically significant spatial clusters.

## Research Questions
- How do Airbnb rental rates vary across different neighbourhoods in New York City?
- How have rental rates changed over time?
- Are there seasonal patterns in Airbnb rental rates?
- Are high and low rental rates geographically clustered?
- How have spatial price clusters changed between 2022 and 2025?

## Objectives
- Analyse the geographical distribution of Airbnb rental rates across NYC.
- Examine monthly trends, seasonal variations and yearly changes.
- Identify spatial clusters and outliers using spatial autocorrelation techniques.
- Compare neighbourhood-level spatial clusters between 2022 and 2025.

## Dataset
Source : Kaggle -- Airbnb Data: New York City 5Y (2021 - 2026)

The dataset contains Airbnb Listing information and historical monthly rental - rate records

Key variables include:
- listing_id — Unique listing identifier
- latitude — Geographic latitude
- longitude — Geographic longitude
- neighborhood — Neighbourhood
- month_date — Historical observation month
- avg_daily_rate — Average daily rental rate

## Methodology

1. Data collection and validation
2.  Data cleaning and validation
3.  Exploratory data analysis
4.  Spatial price analysis
5.  Temporal trend and seasonal analysis
6.  Global spatial autocorrelation using Moran's I
7.  Local spatial cluster analysis using Local Moran's I (LISA)
8.  Comparison of spatial clusters between 2022 and 2025
   

## Data Source and Licence
The raw data is **not included** in this repository. See [`data/README.md`](data/README.md) for the download source, licence and instructions.

Airbnb data: Jason_AirROI (data sourced from AirROI), Kaggle, licensed CC BY-NC 4.0. Used here for non-commercial academic purposes.

## Repository Structure
- `data/`: dataset instructions (raw and processed data are kept locally)
- `notebooks/`: Jupyter notebooks for each analysis stage
- `src/`: reusable Python code
- `outputs/`: figures and result tables
- `maps/`: final map images
- `report/`: final report and presentation

## How to Reproduce
1. Clone this repository.
2. Create and activate a virtual environment, then install the packages:
   `python -m venv .venv`, then `.venv\Scripts\Activate.ps1` (Windows), then `python -m pip install -r requirements.txt`
3. Download the data as described in `data/README.md` and place it in `data/raw/`.
4. Run the notebooks in `notebooks/` in numerical order.

## Project Status
In progress. Project setup is complete; data validation and analysis are under way.