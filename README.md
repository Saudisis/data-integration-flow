# AQA Data Integration Pipeline

**Interactive Workflow for ARPA + ERA5 + Sentinel-5P Integration**  
This repository documents the automated pipeline for integrating air quality and meteorological data across the Milan Metropolitan Area (AOI).

---

## Overview

The **AQA Data Integration Pipeline** automates the acquisition, processing, harmonization, and export of environmental datasets from multiple open sources:

- **ARPA Lombardia** (Ground sensors for pollutants)
- **ERA5** (Reanalysis meteorological data from ECMWF)
- **Sentinel-5P** (Satellite-based air quality indicators via Google Earth Engine)

The pipeline aggregates hourly and daily data, computes temporal windows (`current` vs `previous`), interpolates values spatially, and exports harmonized datasets for scientific and visualization purposes.

---

## Workflow Stages

| Stage | Description |
|:------|:-------------|
| 1️⃣ | **Metadata & Configuration** — Define AOI, bounding box, start/end dates, and pollutants. |
| 2️⃣ | **ARPA Download** — Fetch ground sensor data and coordinates from open Lombardia API. |
| 3️⃣ | **ERA5 Download** — Retrieve meteorological variables (temperature, pressure, precipitation, wind, etc.). |
| 4️⃣ | **Sentinel-5P Extraction** — Query satellite NO₂, CO, SO₂, and O₃ columns via Google Earth Engine. |
| 5️⃣ | **Grid Generation** — Build spatial grid based on ARPA sensor spacing. |
| 6️⃣ | **Interpolation** — Bilinear interpolation of ERA5 data to grid coordinates. |
| 7️⃣ | **Fusion** — Combine ground, satellite, and reanalysis datasets by time window. |
| 8️⃣ | **Export & Visualization** — Output harmonized CSV and GeoDataFrame ready for mapping or analysis. |

---

## Data Sources

| Source | Access Method | Format |
|:--------|:--------------|:--------|
| **ARPA Lombardia** | [dati.lombardia.it](https://www.dati.lombardia.it) | JSON / CSV |
| **ERA5** | [CDS API (Copernicus)](https://cds.climate.copernicus.eu/api-how-to) | NetCDF |
| **Sentinel-5P** | [Google Earth Engine](https://developers.google.com/earth-engine/datasets/catalog/sentinel-5p) | GeoTIFF / Cloud asset |

---

## Technologies Used

- **Python** (`pandas`, `xarray`, `geopandas`, `rioxarray`, `cdsapi`, `requests`, `matplotlib`)
- **Google Earth Engine API**
- **Jupyter Notebooks**
- **Mermaid.js** (for interactive diagrams)
- **GitHub Pages** (for publishing visual workflows)

---

## Included Visual Diagrams

| Section | Diagram |
|:--------|:---------|
| 1️⃣ | BPMN Process Flow |
| 2️⃣ | Entity–Relationship Schema |
| 3️⃣ | Block Architecture Diagram |
| 4️⃣ | UML Use Case Diagram |
| 5️⃣ | UX / User Flow |

All diagrams are interactive and available on  
**[saudisis.github.io/data-integration-flow](https://saudisis.github.io/data-integration-flow/)**

---

## Project Structure

├── README.md
├── index.html ← Main interactive documentation page
├── aqa_pipeline_workflow.html ← Secondary visualization (pipeline)
├── data_integration_flow.html ← Detailed flow for data processing
