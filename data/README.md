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

## NYC neighbourhood boundaries

- **Name:** 2020 Neighborhood Tabulation Areas (NTAs)
- **Publisher:** NYC Department of City Planning (DCP), via NYC Open Data
- **Source:** https://data.cityofnewyork.us/d/9nt8-h7nd
- **Downloaded:** 19 November 2026, as GeoJSON (Export from the page above)
- **Local file:** `data/raw/nta2020.geojson` (renamed from the original download)
- **Edition:** not recorded in the file itself; DCP's current metadata document lists edition 26D
- **Contents:** 262 polygons, CRS EPSG:4326 in the exported file
- **`ntatype` codes (DCP metadata):** 0 Residential, 5 Rikers Island, 6 Other special areas, 7 Cemetery, 8 Airport, 9 Park
- **Caveat (DCP):** NTAs approximate neighbourhoods and are not intended to definitively represent them.

## Folders

- `data/raw/`: original downloads. Never edited. Not uploaded to GitHub.
- `data/processed/`: cleaned data produced by the notebooks. Not uploaded to GitHub.