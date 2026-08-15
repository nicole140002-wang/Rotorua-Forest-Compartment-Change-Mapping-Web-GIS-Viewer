# Rotorua-Forest-Compartment-Change-Mapping-Web-GIS-Viewer

An end-to-end forestry GIS project using LINZ multi-temporal aerial imagery, ArcGIS Pro and ArcGIS Maps SDK for JavaScript to review forest compartment changes and present the results in an interactive before/after Web GIS viewer.

## Final Output

<img width="2545" height="1347" alt="image" src="https://github.com/user-attachments/assets/71964922-cf15-42f2-97dd-0a47c153df25" />

## Project Overview
Two aerial imagery periods were compared:
**Historical imagery**: 2015–2017([Bay of Plenty 0.25m Rural Aerial Photos (2015-2017)](https://data.linz.govt.nz/layer/88130-bay-of-plenty-025m-rural-aerial-photos-2015-2017/))
**Recent imagery**: 2024–2025([Bay of Plenty West 0.2m Rural Aerial Photos (2024-2025)](https://data.linz.govt.nz/layer/120065-bay-of-plenty-west-02m-rural-aerial-photos-2024-2025/))

A Rotorua study area containing 38 forest compartments was reviewed and updated based on visible forestry and land-cover changes.

The workflow included:

**Aerial imagery → compartment review → attribute update → topology/QA → Web GIS visualisation.**

## Key Questions
This project focuses on three practical GIS questions:

**(1) How has forest condition changed between the 2015–2017 and 2024–2025 imagery periods?
(2) Which forest compartments require spatial or attribute updates?
(3) How can the identified changes be communicated efficiently through an interactive Web GIS application?**

## Data Sources
| Dataset | Period | Source | Purpose |
|---|---|---|---|
| Rural Aerial Imagery | 2015–2017 | LINZ | Historical baseline imagery |
| Rural Aerial Imagery | 2024–2025 | LINZ | Recent imagery used for compartment review |
| Forest Compartments | Project-derived | Digitised / updated in ArcGIS Pro | Forestry compartment boundaries and attributes |
| Study Area | Project-derived | GIS project boundary | Defines the analysis and Web GIS display extent |

### Coordinate Reference System

Primary GIS analysis:
**NZGD2000 / New Zealand Transverse Mercator 2000 — EPSG:2193**

Web GeoJSON layers:
**WGS 84 — EPSG:4326**

## GIS Workflow
### 1. Imagery preparation

LINZ Rural Aerial Imagery was prepared and mosaic in ArcGIS Pro.
Large TIFF imagery was converted to **Cloud Optimized GeoTIFF (COG)** for Web GIS use.

### 2. Compartment review
38 forest compartments were visually reviewed against the 2024–2025 imagery.
Attributes recorded include:

| compartment ID | 
| area | 
| historical status | 
| recent status | 
| change type | 
| change confidence | 
| change description | 

### 3. 
