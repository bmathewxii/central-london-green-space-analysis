# Satellite Imagery Analysis - Central London Green Spaces

This project analyses green space coverage using satellite imagery across 10 boroughs in central London. The scripts processes Sentinel-2 data to calculate the Normalized Difference Vegetation Index (NDVI) - a differential measure based on the reflection of near-infared and red light.

## Data Sources
- London borough boundaries: https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london
- Sentinel-2 data: https://dataspace.copernicus.eu/explore-data/data-collections/sentinel-data/sentinel-2

## Analysed Boroughs
This analysis focuses on 10 central London boroughs (this can be configured in the code if needed): 

- City of London
- Westminster
- Camden
- Islington
- Southwark
- Kensington and Chelsea
- Lambeth
- Tower Hamlets
- Hackney
- Wandsworth


## Requirements

- Python 3.8+
- Dependencies:
  - geopandas
  - rasterio
  - numpy
  - pandas
  - matplotlib
  - scikit-image

You can install the required packages using:

```bash
pip install -r requirements.txt
```

## Data Preparation

To run this analysis, you'll need to:

1. Download Sentinel-2 imagery from https://dataspace.copernicus.eu/explore-data/data-collections/sentinel-data/sentinel-2 
2. Download London borough boundaries from https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london
3. Ensure folder structure consistent with code

## Usage

The analysis is performed through a sequence of three scripts:

### 1. Process London Borough Boundaries

```bash
python Scripts/process_london_boundaries.py
```

This script processes the London borough boundary shapefiles, extracting central London boroughs and creating visualisations. It prepares the boundaries for further analysis.

### 2. Clip Sentinel-2 Data

```bash
python Scripts/clip_sentinel_data.py
```

This script clips the Sentinel-2 satellite imagery to the London boundaries processed in step 1. It extracts the required spectral bands (Red and Near-Infrared) for NDVI calculation.

### 3. Calculate NDVI

```bash
python Scripts/calculate_ndvi.py
```

This script calculates the Normalised Difference Vegetation Index (NDVI) from the processed Sentinel-2 bands and performs spatial analysis to quantify green space coverage across central London boroughs.

## Results

Reuslts have been saved down on the Results folder as part of this repo - analysis produces several types of visualisations and data:

Boundary Processing Outputs:
- Map of selected central London boroughs
- Area statistics for each borough in tabular format

Sentinel-2 Processing Outputs:
- Previews of processed spectral bands
- Sattelite view of selected boroughs

NDVI Analysis Outputs:
- NDVI maps showing vegetation density across Central London
- CSV of Borough-level statistics on green space coverage
- NDVI distribution histograms
- Binary vegetation masks showing green areas
- Maps of distinct green spaces
- Green space size by borough bar chart
- Choropleth maps comparing green space percentage by borough

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

If you have any questions or feedback, please open an issue in this repository or reach out to me on github.
