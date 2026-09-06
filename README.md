# Urban Heat Island Effect – Port Harcourt City LGA

## Project Overview

This project analyses the Urban Heat Island (UHI) effect in Port Harcourt City Local Government Area by combining:
- **Land surface temperature** from satellite thermal imagery
- **Vegetation health** using NDVI (Normalised Difference Vegetation Index)

The analysis identifies which areas experience the highest temperatures and how vegetation cover influences temperature patterns.

## Problem Statement

Rapid urbanisation in Port Harcourt is creating heat islands that affect public health, energy use, and quality of life. This project provides evidence to help decision-makers implement cooling strategies such as:
- Tree planting
- Green space development
- Cool roof initiatives

## Data Sources

| Dataset | Source |
|---------|--------|
| Administrative boundaries | [GRID3 Nigeria](https://grid3.org/datasets?country=nigeria) |
| Landsat 8 / Sentinel-2 thermal bands | [USGS Earth Explorer](https://earthexplorer.usgs.gov/) |
| Landsat 8 / Sentinel-2 visible/NIR bands | [USGS Earth Explorer](https://earthexplorer.usgs.gov/) |
| Settlement extents | [GRID3 Nigeria](https://grid3.org/datasets?country=nigeria) |

## Methodology

### Step 1: Download Satellite Imagery
- Landsat 8 or Sentinel-2 images covering Port Harcourt
- Thermal bands for temperature calculation
- Visible/NIR bands for NDVI calculation

### Step 2: Calculate Land Surface Temperature
- Convert thermal bands to temperature values

### Step 3: Calculate NDVI
- Use visible and near-infrared bands to assess vegetation health

### Step 4: Correlate Temperature and Vegetation
- Identify where temperatures are highest and vegetation is lowest

## Repository Structure

- `project-brief.md` – Project description and data sources
- `data/` – Raw satellite imagery (to be added)
- `scripts/` – Analysis code (to be added)
- `outputs/` – Temperature maps and reports (to be added)

## Future Development

A **urban heat monitoring dashboard** that:
- Updates automatically when new satellite imagery is available
- Shows temperature trends over time
- Identifies new heat hotspots
- Generates reports for urban planners

## Author

Grace Martins-Ateli
GeoDev Lab Africa – Month 1 – Week 1
