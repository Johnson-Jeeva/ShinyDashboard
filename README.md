# GeoSpatial Analysis of Abandoned Properties and Public Facilities with Census Data in South Bend

## Overview
This project is a web-based application built using **R Shiny** to visualize and analyze geospatial data on abandoned properties, public facilities, and census demographic data in **South Bend, Indiana**. The goal of this analysis is to help understand patterns in property abandonment and their relationship to public infrastructure and community demographics.

## Features
- **Interactive Mapping**: Dynamic Leaflet map to explore abandoned properties, census data, and public facilities.
- **Filter Options**: Filter data by property status, facility type, population density, housing occupancy, and racial demographics.
- **Geospatial Layers**: Visualizes multiple layers of geographic data, including census tract polygons and points for public facilities.

## Datasets
This project incorporates the following datasets:

1. **Abandoned Properties Dataset**
   - **Description**: Information on abandoned properties in South Bend, including property details and current status.
   - **Rows**: 1428
   - **Columns**: 
     - `Structures`: Number of abandoned structures on the property
     - `Outcome_St`: Status of the property (e.g., vacant, demolished)
     - `Zip_Code`: Zip code of the property
     - `Council_Di`: Council district where the property is located

2. **Census Data (2010)**
   - **Description**: Census data detailing population statistics, housing units, and racial demographics.
   - **Rows**: 29 (Census tracts)
   - **Columns**:
     - `TRACTCE`: Census tract code
     - `Pop_Den`: Population density of the tract
     - `Pct_Occ`: Percentage of housing units occupied
     - `Pct_White`: Percentage of White population in the tract
     - `Pct_Non_White`: Percentage of Non-White population in the tract

3. **Public Facilities Data**
   - **Description**: Locations of public facilities like fire stations, police stations, and libraries in South Bend.
   - **Rows**: 41
   - **Columns**:
     - `POPL_TYPE`: Type of public facility (e.g., fire station, library)
     - `POPL_NAME`: Name of the facility
     - `Lat`: Latitude of the facility
     - `Lon`: Longitude of the facility

## Common Columns Across Datasets
- **Geospatial data**: The datasets share geographic identifiers, enabling their integration for spatial analysis. Specifically, the `Zip_Code` in the Abandoned Properties dataset corresponds with locations that can be mapped to public facilities and census tracts.

## Application Structure
- **User Interface**: Offers a sidebar for selecting filters (property status, facility type, demographic variables) and displays the results on a Leaflet map.
- **Server Logic**: Processes the selected filters and updates the map with the filtered data.
- **Map Features**: Each dataset is represented by a separate layer on the map, with abandoned properties as points and census tracts as polygons.

## Requirements
To run this project locally, ensure you have the following R packages installed:

```r
install.packages(c("shiny", "tidyverse", "sf", "leaflet", "dplyr", "ggmap"))
