# Data

The raw data files are **not stored in this repository**. They are kept locally in `data/raw/`.

## Airbnb dataset

- **Name:** Airbnb Data: New York City 5Y (2021-26)
- **Provider:** Jason_AirROI (data sourced from AirROI)
- **Source:** https://www.kaggle.com/datasets/jasonairroi/airbnb-short-term-rental-data-new-york-city
- **Licence:** 
Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0), as shown on the Kaggle dataset page. Used here for non-commercial academic purposes, with attribution to the author (Jason_AirROI; data sourced from AirROI).

### Files used (place in `data/raw/`)

- `listings.parquet`
- `listings_monthly.csv`
- `past_rates.csv`
- `past_rates.parquet`

### How to obtain

1. Open the Kaggle link above (a free Kaggle account is required).
2. Click **Download** and extract the zip file.
3. Copy the four files listed above into `data/raw/`.

## NYC neighbourhood boundaries

To be added once the boundary dataset has been downloaded and validated
(planned source: NYC Department of City Planning, 2020 Neighborhood Tabulation Areas, via NYC Open Data).

## Folders

- `data/raw/`: original downloads. Never edited. Not uploaded to GitHub.
- `data/processed/`: cleaned data produced by the notebooks. Not uploaded to GitHub.