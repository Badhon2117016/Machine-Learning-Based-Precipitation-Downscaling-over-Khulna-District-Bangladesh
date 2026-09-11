# Corrected Khulna precipitation-downscaling notebooks

Run in order:

1. 00_Project_Setup_FIXED.ipynb
2. 01_Data_Inventory_FIXED.ipynb
3. 02_Gauge_Preprocessing_FIXED.ipynb
4. 03_Precipitation_Preprocessing_FIXED.ipynb
5. 04_Land_Surface_Preprocessing_FIXED.ipynb
6. 05_TestYear_Target_Grid_Alignment_FIXED.ipynb
7. 06_Station_Value_Extraction_NATIVE_FIXED.ipynb
8. 07_Khulna_Paper_Style_FINAL_FIXED.ipynb

Core corrections:
- Native-resolution precipitation extraction for training/validation/test stations.
- No all-year NDVI-grid alignment.
- No edge clamping.
- No nearest fill of large NoData gaps.
- Exact paper-style Comb1 and Comb2 feature definitions.
- Standalone PERSIANN excluded; CDR treated as PERSIANN-CDR.
- LST Night intentionally excluded for this adapted Khulna workflow.
- Test year 2022 only is aligned to one spatial prediction grid.
- Old output reuse disabled by default in final modelling.
- 0.005 degree described as output grid spacing, not guaranteed effective data resolution.
