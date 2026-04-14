# Raster-Analysis
 Raster Analysis &amp; Cost Surface Modelling
# Raster Analysis & Cost Surface Modelling

This project demonstrates applied raster analysis in Python, replicating an ArcGIS Pro GIS Fundamentals workflow entirely in a Jupyter Notebook environment using `rasterio`, `numpy`, `scipy`, and `geopandas`. Two analytical projects are implemented: (1) multi-resolution DEM mosaicking and spike/pit error correction via low-pass filtering and conditional raster algebra on the Mount Shasta (California) DEM, and (2) a least-cost surface model for road construction in Duluth, Minnesota, integrating an exponential slope-cost function and Euclidean distance-from-roads cost layer, culminating in a $25,000 budget threshold mask and a publication-quality 4-panel cartographic output.

## Skills demonstrated
- Raster resampling (bilinear) and multi-resolution DEM combination using conditional logic (`np.where` ≡ ArcGIS `Con/IsNull`)
- Low-pass neighbourhood filtering and selective cell replacement for DEM error correction
- Percent slope derivation from gradient arrays (`np.gradient`)
- Euclidean distance raster generation via `scipy.ndimage.distance_transform_edt`
- Permanent reclassification and binary masking for cost threshold analysis
- Cartographic layout design: hillshade overlay, graduated colour ramps, north arrow, scale bar

## Data
DEM tiles (valley3, valley9, Shasta, DulNorthDEM) and DuluthNorthRoads shapefile — NAD83 UTM Zone 15N (EPSG:26915) and Zone 11N (EPSG:26910)

## Outputs
| Map | Description |
|---|---|
| `Map1_Shasta_Elevation.pdf` | Filtered elevation + semi-transparent hillshade, Mount Shasta CA |
| `Map2_CostSurface_4panel.pdf` | Distance cost · Slope cost · Budget mask · Final cost — Duluth MN |

## How to run
```bash
pip install rasterio numpy scipy matplotlib geopandas
jupyter notebook Lab9_Raster_Analysis.ipynb
```

*Part of PhD coursework in Geography & GIS — University of Cincinnati*  
*Author: Tolulope Oladeji · github.com/tadedoyinsola*
