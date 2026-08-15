<img width="2545" height="1347" alt="image" src="https://github.com/user-attachments/assets/ef1b72fe-d0da-48f5-aa74-85713afc1992" /># Rotorua-Forest-Compartment-Change-Mapping-Web-GIS-Viewer

A geospatial forestry mapping and Web GIS project using multi-temporal LINZ rural aerial imagery to review forest compartment changes in a Rotorua study area, update compartment attributes and boundaries, perform spatial QA/QC, and communicate changes through an interactive before/after imagery viewer.

The project demonstrates a practical workflow from **aerial imagery interpretation and GIS data maintenance through to interactive Web GIS delivery**.

<img width="2545" height="1347" alt="image" src="https://github.com/user-attachments/assets/71964922-cf15-42f2-97dd-0a47c153df25" />

## Project Overview
Forest estate spatial information needs to be periodically reviewed as harvesting, regeneration, replanting, road development and land-cover change can make existing compartment information outdated.
This project develops a small Rotorua forestry demonstration workflow using two generations of rural aerial imagery:
**Historical imagery**: 2015–2017([Bay of Plenty 0.25m Rural Aerial Photos (2015-2017)](https://data.linz.govt.nz/layer/88130-bay-of-plenty-025m-rural-aerial-photos-2015-2017/))
**Recent imagery**: 2024–2025([Bay of Plenty West 0.2m Rural Aerial Photos (2024-2025)](https://data.linz.govt.nz/layer/120065-bay-of-plenty-west-02m-rural-aerial-photos-2024-2025/))

A study area was defined in the Rotorua / Bay of Plenty region and 38 forest compartments were reviewed using the recent aerial imagery.
Compartment geometry and attributes were updated based on visible land-cover and forestry changes, followed by topology and geometry QA/QC.

The updated forest compartment layer was then integrated with both imagery periods in an ArcGIS Maps SDK for JavaScript Web GIS viewer, allowing users to interactively compare historical and recent imagery using a swipe interface.

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

The ArcGIS Maps SDK handles projection between the Web GIS vector layers and imagery spatial reference during visualisation.
