# README

## Project Title

**Spatial Inequality in Urban Green Space and Heat Exposure: Evidence from Dhaka, Bangladesh**

---

## Project Overview

This project analyzes spatial inequality in vegetation cover, built-up intensity, and land surface temperature (LST) across Dhaka using satellite imagery, population data, and spatial statistics.

The workflow consists of:

1. Satellite data preprocessing and raster export using Google Earth Engine
2. Spatial statistical analysis in Python

---

## Files

### 1. `eda.js`

Google Earth Engine script used for:

* Landsat 8/9 preprocessing
* Cloud masking
* NDVI, NDBI, and LST calculation
* Initial exploratory visualization
* Raster export for downstream analysis

### 2. `stats.py`

Main spatial analysis pipeline used for:

* 1 km grid creation
* Zonal statistics extraction
* Population-weighted exposure analysis
* OLS regression analysis
* Spatial autocorrelation analysis:

  * Global Moran’s I
  * Local Moran’s I (LISA)
  * Getis-Ord Gi* hotspot analysis
* Figure and output generation

---

## Required Libraries

### Google Earth Engine (`eda.js`)

The following platform/library was used but not covered in class:

* Google Earth Engine (GEE)

Run the script in:

* [Google Earth Engine Code Editor](https://code.earthengine.google.com?utm_source=chatgpt.com)

---

### Python Libraries (`stats.py`)

Install dependencies using:

```bash
pip install geopandas rasterstats rasterio pysal esda libpysal statsmodels matplotlib seaborn numpy pandas
```

Main libraries used:

* `geopandas`
* `rasterstats`
* `rasterio`
* `numpy`
* `pandas`
* `matplotlib`
* `statsmodels`
* `libpysal`
* `esda`

---

## How to Run

### Step 1 — Run `eda.py`

1. Execute the workflow
2. Export generated rasters (NDVI, NDBI, LST, etc.)

Note: the exported rasters are already downloaded in raster's folder. It will be difficult to run the eda.py as it requires my credentials where the assets are stored.

### Step 2 — Run `stats.py`

After exporting rasters and preparing input files:

```bash
python stats.py
```

This script performs:

* Grid generation
* Spatial statistics
* OLS regression
* Moran’s I analysis
* LISA clustering
* Getis-Ord Gi* hotspot analysis
* Visualization and output export

---

## Outputs

The project generates:

* Spatial distribution maps
* Moran scatterplots
* Hotspot/coldspot maps
* OLS diagnostic plots
* Population-weighted exposure statistics
* Final processed spatial datasets

---

## Notes

* Coordinate Reference System (CRS): EPSG:32645
* Analysis resolution: 1 km grid
* Population dataset: WorldPop 2024
* Satellite source: Landsat 8 & 9 Collection 2 Level 2 data
