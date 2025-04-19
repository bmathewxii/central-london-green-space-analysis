# Central London Green Space Analysis

This project analyses green space coverage across 10 boroughs in central London using satellite imagery and Python. It identifies parks, gardens, and vegetation areas within central boroughs, creates visuals to show results.

## Data Sources
- London borough boundaries: https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london
- Sentinel-2 data: https://dataspace.copernicus.eu/explore-data/data-collections/sentinel-data/sentinel-2

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

## Project Structure

project/
├── Data/                        # Data storage (not included in repo)
│   ├── Raw/                     # Original satellite images and boundaries
│   └── Processed/               # Processed data files
├── Results/                     # Output visualisations and statistics
├── Scripts/                     # Python scripts
│   ├── process_london_boundaries.py   # Process borough boundaries
│   ├── clip_sentinel_data.py          # Clip satellite imagery to boundaries
│   └── calculate_ndvi.py              # Calculate vegetation indices and statistics
└── README.md                    # Project documentation

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

## Data Preparation

To run this analysis, you'll need to:

1. Download Sentinel-2 imagery from https://dataspace.copernicus.eu/explore-data/data-collections/sentinel-data/sentinel-2 
2. Download London borough boundaries from https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london
3. Place the data in the appropriate folders

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

The analysis produces several types of visualisations and data:

Boundary Processing Outputs:
- Maps of selected central London boroughs and combined boundaries
- Area statistics for each borough in tabular format

Sentinel-2 Processing Outputs:
- Previews of processed spectral bands
- True color composite images of central London

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
