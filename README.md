# GIS-Based Site Suitability Analysis

## Solar-Powered Seismic Monitoring Station

### Project Overview

This project explores the use of Geographic Information Systems (GIS) to evaluate terrain suitability for a potential seismic monitoring station within a protected natural landscape.

Originally developed as a terrain-based construction suitability exercise, the analysis has been adapted into a research-oriented site-selection case study. The proposed application considers the placement of a seismometer and supporting solar-powered infrastructure while minimizing potential disturbance to the surrounding environment.

The project demonstrates raster processing, terrain analysis, spatial reclassification, multicriteria modeling, and geospatial visualization using QGIS.

### Featured Analysis

![Combined terrain suitability with hillshade context](https://github.com/GNSS-GLOBAL/qgis_spatial_analysis/blob/main/solar_seismic_monitoring_station/images/all_conditions_w_hillshade.png)

*Combined terrain suitability visualization with hillshade context. The classification reflects the modeled slope and aspect criteria, not a validated seismic station location.*

## Research Objectives

* Identify terrain satisfying selected slope and aspect criteria.
* Evaluate topographic characteristics relevant to site accessibility and infrastructure placement.
* Combine individual terrain criteria into a composite suitability raster.
* Investigate the potential application of terrain modeling to remote seismic monitoring infrastructure.
* Establish a reproducible GIS workflow for future site-selection studies.

## Technologies and Tools

|Technology|Application|
|-|-|
|QGIS|Spatial analysis and visualization|
|GDAL|Raster processing and terrain analysis|
|SRTM DEM|Source elevation dataset|
|GeoTIFF|Raster data storage|
|Raster Calculator|Conditional classification and suitability modeling|
|EPSG:4326|Original SRTM raster coordinate reference system|
|EPSG:32733|Projected coordinate reference system (WGS 84 / UTM Zone 33S)|

## Methodology

### 1\. Elevation Data Preparation

An SRTM digital elevation model (DEM) serves as the primary elevation dataset.

Terrain derivatives are generated from the elevation surface to evaluate geographic characteristics relevant to site selection.

![SRTM elevation surface rendered with pseudocolor](https://github.com/GNSS-GLOBAL/qgis_spatial_analysis/blob/main/solar_seismic_monitoring_station/images/pseudocolor_srtm.png)

*Source elevation surface with pseudocolor rendering to reveal regional terrain variation.*

### 2\. Terrain Analysis

Three principal terrain products are used:

**Slope**

* Represents terrain steepness.
* Supports identification of relatively flat areas.
* Provides a basis for evaluating construction accessibility and potential installation locations.

**Aspect**

* Represents the compass direction that terrain faces.
* Supports directional terrain classification.
* Can inform preliminary solar infrastructure planning, subject to additional solar exposure analysis.

**Hillshade**

* Simulates terrain illumination to highlight relief.
* Improves visual interpretation of the landscape.
* Supports cartographic presentation of the study area.

### 3\. Raster Reclassification

Terrain characteristics are converted into conditional raster outputs.

The original modeling workflow includes:

* Slope thresholds of 2° and 5°
* North-facing aspect classification
* Raster-based evaluation of individual suitability criteria

These criteria originate from the initial terrain suitability exercise and do not independently establish suitability for seismic instrumentation or solar energy production.

![Terrain classification using a five-degree maximum slope](https://github.com/GNSS-GLOBAL/qgis_spatial_analysis/blob/main/solar_seismic_monitoring_station/images/slope_lte5.png)

*Terrain classification using a slope threshold of 5°.*

![North-facing aspect classification](https://github.com/GNSS-GLOBAL/qgis_spatial_analysis/blob/main/solar_seismic_monitoring_station/images/aspect_north.png)

*Aspect classification highlighting terrain that meets the north-facing directional criterion.*

### 4\. Multicriteria Suitability Modeling

Reclassified terrain rasters are combined to identify areas satisfying the selected conditions.

The resulting `all_conditions.tif` raster represents the combined terrain suitability model.

This output demonstrates how multiple spatial constraints can be incorporated into a single analytical result.

![Combined terrain suitability classification](https://github.com/GNSS-GLOBAL/qgis_spatial_analysis/blob/main/solar_seismic_monitoring_station/images/all_conditions.png)

*Combined classification before hillshade is used to provide additional visual context.*

### 5\. Cartographic Interpretation

The resulting terrain products are examined using QGIS.

Hillshade and elevation-derived layers provide geographic context, while classified raster outputs help distinguish areas satisfying the modeled conditions.

## Proposed Research Application

### Seismic Monitoring Infrastructure

A remote seismic monitoring station requires careful site selection to support reliable measurements and minimize environmental disturbance.

Additional evaluation would include:

* Geological stability and ground coupling
* Ambient vibration and seismic noise
* Accessibility and maintenance requirements
* Environmental restrictions within protected landscapes
* Communications and telemetry infrastructure

### Solar Power Infrastructure

Solar energy could support a remote monitoring installation where conventional electrical infrastructure is unavailable.

Future modeling could incorporate:

* Solar irradiance
* Terrain orientation and shading
* Seasonal solar exposure
* Battery and energy storage requirements
* Separation between seismometer and power equipment

The optimal seismometer location may differ from the optimal solar installation location, creating an opportunity for additional spatial optimization.

## Results and Interpretation

The completed terrain analysis demonstrates the integration of slope and aspect classifications into a combined spatial suitability output.

The results identify areas satisfying the original terrain criteria, providing a foundation for investigating more specialized research infrastructure requirements.

Further analysis would be required before recommending a physical installation location.

## Project Structure

```text
qgis_spatial_analysis/
├── README.md
├── .gitattributes
└── solar_seismic_monitoring_station
    ├── seismograph_station_construction.qgz
    ├── images/
    │   ├── all_conditions_w_hillshade.png
    │   ├── all_conditions.png
    │   ├── pseudocolor_srtm.png
    │   ├── slope_lte5.png
    │   └── aspect_north.png
    └── rasters/
        ├── srtm_41_19_4326.tif
        ├── all_conditions.tif
        ├── aspect
        ├── slope
        └── hillshade
```

The raster subdirectories contain supporting terrain-analysis outputs and associated metadata. The `images/` directory contains curated map exports for portfolio presentation; local troubleshooting logs are not included.

## Future Development

* Incorporate geological and seismic-noise datasets.
* Model solar irradiation and terrain shading.
* Introduce environmental exclusion zones.
* Evaluate infrastructure access and maintenance routes.
* Compare multiple candidate sites using weighted suitability criteria.
* Extend the visual analysis with a dedicated cartographic layout and documented spatial criteria.

## Key Skills Demonstrated

* GIS terrain modeling
* Digital elevation model processing
* Raster reclassification
* Multicriteria spatial analysis
* Spatial data organization
* Geospatial troubleshooting
* Cartographic interpretation
* Research-oriented site suitability assessment

## Project Status

**Terrain analysis completed; research application under development.**

This project is an analytical case study and does not represent a validated engineering or seismic monitoring station design.

## Author

**CJ | GNSS-GLOBAL**

Data \& Geospatial Analyst  
FAA Part 107 Certified Remote Pilot

[LinkedIn](https://www.linkedin.com/in/christiann-l-118662184/) | [GitHub](https://github.com/GNSS-GLOBAL)

