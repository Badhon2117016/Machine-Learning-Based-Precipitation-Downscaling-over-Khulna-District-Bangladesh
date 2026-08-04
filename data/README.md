# Data Directory

This directory contains all datasets used in the **Precipitation Downscaling for Khulna District, Bangladesh** project.

## Folder Structure

### `raw/`

Contains the original datasets exactly as downloaded from their source. These files should never be modified.

Contents include:

* Administrative boundary
* Rain gauge observations
* Satellite precipitation products
* DEM
* NDVI
* Land Surface Temperature
* Land Use/Land Cover
* Other environmental predictors

---

### `interim/`

Contains temporary datasets generated during preprocessing.

Typical operations include:

* clipping
* reprojection
* resampling
* raster alignment
* quality control
* temporary outputs

These files can be regenerated at any time.

---

### `processed/`

Contains datasets ready for modelling and analysis.

Examples include:

* aligned rasters
* monthly predictor stacks
* extracted station samples
* machine-learning training tables
* prediction rasters
* evaluation tables

---

## Data Sources

The project uses publicly available datasets, including:

* CHIRPS
* PERSIANN-CDR
* PERSIANN-CCS
* PDIR-Now
* GSMaP
* IMERG
* ERA5
* SRTM DEM
* MODIS NDVI
* MODIS Land Surface Temperature
* ESA WorldCover (or equivalent LULC dataset)

Please consult each data provider for licensing and citation requirements.

---

## Notes

Large raster datasets are intentionally excluded from this GitHub repository using `.gitignore`.

Users should download the original datasets from their official providers before running the workflow.
