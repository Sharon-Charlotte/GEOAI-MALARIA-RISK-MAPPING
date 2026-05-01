# GEOAI-MALARIA-RISK-MAPPING  
## Overview
This project uses machine learning and geospatial analysis to map
malaria risk across Kampala district, Uganda. Three models are
compared — Random Forest, Logistic Regression, and a Neural Network.

## Data used
| Layer | Source | Purpose |

| DEM (KampalaCityDEM.tif) | Local dataset | Elevation, slope, TWI |
| Kampala boundary (.shp) | Local dataset | Study area mask |
| Waterbody (.shp) | Local dataset | Distance to water feature |
| Landcover (Sentinel-2) | Uganda 2014 | Vegetation proxy |

## Features engineered
- Elevation (metres)
- Slope (gradient)
- Distance to nearest waterbody (pixels)
- Vegetation presence (landcover class 3 = vegetated)

## Model results
| Model | AUC |
|---|---|
| Random Forest | 1.000 |
| Neural Network | 0.9852 |
| Logistic Regression | 0.9692 |

## Risk map
<img width="1989" height="1068" alt="malaria_risk_map_kampala" src="https://github.com/user-attachments/assets/0e25ac71-8b0b-4ed9-acd6-ff166fbf77d1" />



The final output classifies every pixel in Kampala into three tiers:
- **Low risk** — high elevation, far from water
- **Medium risk** — transitional zones
- **High risk** — low elevation, close to wetlands/waterbodies

Known high-risk zones include Bwaise, Kinawataka, and the
Nakivubo channel corridor — consistent with existing flood
and malaria burden literature for Kampala.

## How to run
1. Open `GEOAI_MALARIA_RISK.ipynb` in Google Colab
2. Mount your Google Drive
3. Update file paths in Cell 4 to point to your data
4. Run all cells top to bottom

## Requirements
rasterio, geopandas, scikit-learn, tensorflow, scipy, numpy, matplotlib
