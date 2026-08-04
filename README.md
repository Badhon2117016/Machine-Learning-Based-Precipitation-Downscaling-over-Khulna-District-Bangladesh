# Machine-Learning-Based-Precipitation-Downscaling-over-Khulna-District-Bangladesh
# Precipitation Downscaling for Khulna District, Bangladesh

## Project Overview

This repository contains a reproducible geospatial and machine-learning workflow for downscaling coarse-resolution precipitation data over Khulna District, Bangladesh.

The project integrates precipitation observations with environmental predictors such as elevation, vegetation indices, land surface temperature, land-use/land-cover, and geographic variables to generate high-resolution monthly precipitation estimates.

## Study Area

The study area is Khulna District, located in southwestern Bangladesh. The region is characterized by coastal influences, low elevation, seasonal monsoon rainfall, river networks, agricultural land, urban areas, and vulnerability to climate-related hazards.

## Objectives

The main objectives of this project are to:

1. Collect and preprocess precipitation and environmental datasets.
2. Align all raster datasets to a common coordinate reference system, spatial resolution, extent, and grid.
3. Create monthly predictor stacks.
4. Extract raster values for model training.
5. Develop statistical and machine-learning downscaling models.
6. Evaluate model performance using appropriate accuracy metrics.
7. generate high-resolution precipitation maps for Khulna District.
8. Analyze spatial and temporal precipitation variability.

## Data Sources

The project may use the following datasets:

| Dataset                 | Purpose                            | Example Source                |
| ----------------------- | ---------------------------------- | ----------------------------- |
| CHIRPS or PDIR-Now      | Coarse-resolution precipitation    | Climate Hazards Center        |
| DEM                     | Elevation and terrain variables    | SRTM / Copernicus DEM         |
| NDVI                    | Vegetation condition               | MODIS                         |
| LST                     | Land surface temperature           | MODIS                         |
| LULC                    | Land-use and land-cover            | ESA WorldCover / MODIS        |
| ERA5-Land               | Climate and atmospheric predictors | Copernicus Climate Data Store |
| Administrative Boundary | Khulna District boundary           | GADM / Bangladesh GIS sources |

Users must review and follow the licensing and citation requirements of each original dataset.

## Repository Structure

```text
Precipitation-Downscaling-Khulna/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── environment.yml
├── requirements.txt
├── .gitignore
│
├── config/
│   └── config.yaml
│
├── data/
│   ├── raw/
│   ├── interim/
│   ├── processed/
│   │   ├── rasters_aligned/
│   │   ├── monthly_stacks/
│   │   ├── training_tables/
│   │   └── predictions/
│   └── external/
│
├── notebooks/
│   ├── 01_Project_Setup.ipynb
│   ├── 02_Data_Inventory.ipynb
│   ├── 03_Boundary_Preparation.ipynb
│   ├── 04_Raster_Preprocessing.ipynb
│   ├── 05_Raster_Alignment.ipynb
│   ├── 06_Quality_Control.ipynb
│   ├── 07_Monthly_Predictor_Stack.ipynb
│   ├── 08_Model_Training.ipynb
│   ├── 09_Model_Evaluation.ipynb
│   └── 10_Prediction_Mapping.ipynb
│
├── src/
│   ├── __init__.py
│   ├── preprocessing.py
│   ├── raster_utils.py
│   ├── quality_control.py
│   ├── feature_engineering.py
│   ├── model_training.py
│   ├── evaluation.py
│   └── visualization.py
│
├── models/
├── outputs/
│   ├── figures/
│   ├── maps/
│   ├── tables/
│   └── reports/
│
├── docs/
└── tests/
```

## Methodology

The general workflow consists of the following stages:

### 1. Data Collection

Precipitation, topographic, climatic, vegetation, temperature, and land-cover datasets are collected for the selected study period.

### 2. Raster Preprocessing

The datasets are:

* clipped to the study area;
* reprojected to a common CRS;
* resampled to a common spatial resolution;
* aligned to a reference raster;
* converted to consistent NoData values;
* organized by year and month.

### 3. Quality Control

Raster quality-control procedures verify:

* CRS;
* width and height;
* pixel resolution;
* affine transform;
* spatial bounds;
* NoData values;
* valid-pixel coverage;
* temporal completeness.

### 4. Predictor-Stack Creation

For each month, the precipitation target and environmental predictor rasters are combined into a consistent raster stack.

### 5. Model Training

Potential downscaling models include:

* Multiple Linear Regression;
* Random Forest Regression;
* Gradient Boosting Regression;
* XGBoost Regression;
* Support Vector Regression.

### 6. Model Evaluation

Model performance may be evaluated using:

* Coefficient of determination, R²;
* Root Mean Squared Error, RMSE;
* Mean Absolute Error, MAE;
* Bias;
* cross-validation;
* spatial validation;
* residual analysis.

### 7. High-Resolution Prediction

The selected model is applied to the predictor rasters to generate high-resolution monthly precipitation maps.

## Installation

### Option 1: Conda

```bash
git clone https://github.com/Badhon2117016/Precipitation_Downscaling_Khulna.git
cd Precipitation_Downscaling_Khulna

conda env create -f environment.yml
conda activate precipitation-downscaling-khulna
```

### Option 2: Pip

```bash
git clone https://github.com/Badhon2117016/Precipitation_Downscaling_Khulna.git
cd Precipitation_Downscaling_Khulna

python -m venv .venv
```

Activate the environment on Windows:

```bash
.venv\Scripts\activate
```

Install the required packages:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Running the Project

Start JupyterLab:

```bash
jupyter lab
```

Run the notebooks sequentially, beginning with:

```text
01_Project_Setup.ipynb
```

The notebooks should be executed according to their numerical order.

## Data Availability

Large raw and processed raster datasets are not stored directly in this GitHub repository.

Users must download the required datasets from their original providers and organize them according to the repository structure.

The following files and directories are excluded from Git tracking:

* raw raster datasets;
* processed GeoTIFF files;
* temporary files;
* trained model files;
* local environments;
* API credentials;
* large intermediate outputs.

## Reproducibility

To improve reproducibility:

* all important file paths should be defined in a configuration file;
* random seeds should be fixed during model training;
* preprocessing parameters should be documented;
* package dependencies should be recorded;
* source datasets and versions should be cited;
* generated outputs should include processing dates and model metadata.

## Expected Outputs

The project is expected to generate:

* aligned raster datasets;
* raster quality-control reports;
* monthly predictor stacks;
* model-training tables;
* model-performance summaries;
* residual plots;
* variable-importance plots;
* high-resolution precipitation rasters;
* monthly and annual precipitation maps;
* spatial and temporal analysis figures.

## Limitations

Potential limitations include:

* uncertainty in satellite-derived precipitation;
* differences in spatial and temporal resolution among datasets;
* missing or cloudy satellite observations;
* limited rain-gauge data for independent validation;
* model sensitivity to predictor selection;
* spatial autocorrelation;
* uncertainty introduced during raster resampling.

## Citation

When using this repository, please cite it using the information provided in the `CITATION.cff` file.

## Author

**Md. Badhon**

GitHub: [Badhon2117016](https://github.com/Badhon2117016)

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
