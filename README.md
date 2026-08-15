# Rotorua-Forest-Compartment-Change-Mapping-Web-GIS-Viewer

An end-to-end forestry GIS project using LINZ multi-temporal aerial imagery, ArcGIS Pro and ArcGIS Maps SDK for JavaScript to review forest compartment changes and present the results in an interactive before/after Web GIS viewer.

## Final Output

<img width="2545" height="1347" alt="image" src="https://github.com/user-attachments/assets/71964922-cf15-42f2-97dd-0a47c153df25" />

## Project Overview
Two aerial imagery periods were compared:
**Historical imagery**: 2015–2017([Bay of Plenty 0.25m Rural Aerial Photos (2015-2017)](https://data.linz.govt.nz/layer/88130-bay-of-plenty-025m-rural-aerial-photos-2015-2017/))
**Recent imagery**: 2024–2025([Bay of Plenty West 0.2m Rural Aerial Photos (2024-2025)](https://data.linz.govt.nz/layer/120065-bay-of-plenty-west-02m-rural-aerial-photos-2024-2025/))

A Rotorua study area containing 38 forest compartments was reviewed and updated based on visible forestry and land-cover changes.
<img width="1594" height="1165" alt="image" src="https://github.com/user-attachments/assets/5d6f976f-ed53-4828-b7ed-62941c142a3d" />

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

The workflow included:

**Aerial imagery → compartment review → attribute update → topology/QA → Web GIS visualisation.**

### 1. Imagery preparation

LINZ Rural Aerial Imagery was prepared and mosaicked in ArcGIS Pro.
Large TIFF imagery was converted to **Cloud Optimized GeoTIFF (COG)** for Web GIS use.

### 2. Compartment review
38 forest compartments were visually reviewed against the 2024–2025 imagery.
Attributes included compartment ID, area, historical status, recent status, change type, change confidence and change description. 

<img width="2161" height="1214" alt="image" src="https://github.com/user-attachments/assets/91b9b797-a73f-4842-9dbe-0047c8e12ed1" />

### 3. Forest Condition Update & QA/QC

Forest compartment boundaries, conditions and attributes were reviewed using the 2015–2017 and 2024–2025 aerial imagery. Geometry, topology and attribute consistency were then checked before the updated layer was prepared for Web GIS use.

Example 1 — Forest condition change

<table> <tr> <td align="center"><b>2015–2017</b></td> <td align="center"><b>2024–2025</b></td> </tr> <tr> <td width="50%"> <img width="100%" alt="Historical aerial imagery 2015-2017" src="https://github.com/user-attachments/assets/e5751a31-2fed-44b5-ac03-6aaf4e129e6d" /> </td> <td width="50%"> <img width="100%" alt="Recent aerial imagery 2024-2025" src="https://github.com/user-attachments/assets/1276955e-ffaa-48fc-8694-17f91422725b" /> </td> </tr> </table>

Comparison: The same compartment area was reviewed across the two imagery periods to identify changes in forest condition and verify whether the existing compartment status and attributes required updating.

Example 2 — Compartment update and validation

<table> <tr> <td align="center"><b>2015–2017</b></td> <td align="center"><b>2024–2025</b></td> </tr> <tr> <td width="50%"> <img width="100%" alt="Historical compartment condition 2015-2017" src="https://github.com/user-attachments/assets/168e52f6-9aaa-4887-b3ed-d6aaec32cfd4" /> </td> <td width="50%"> <img width="100%" alt="Updated compartment condition 2024-2025" src="https://github.com/user-attachments/assets/bba48ac5-a20b-4492-b7d4-412cf50035b8" /> </td> </tr> </table>

Comparison: Historical and recent imagery were compared to confirm visible forestry change, update compartment attributes where required, and check that the final geometry remained consistent with observable forest boundaries.

### 4. Web GIS
An interactive viewer was developed using ArcGIS Maps SDK for JavaScript.
Key functions include:

(1) Before / After imagery swipe
(2) Study-area imagery clipping
(3) Forest compartment overlay
(4) Compartment selector
(5) Automatic zoom
(6) Selected-feature highlighting
(7) Fixed attribute popup
<img width="1807" height="1116" alt="image" src="https://github.com/user-attachments/assets/c68ae888-1fd9-4921-a166-af019500519a" />

## Results

38 compartments reviewed
Final change statistics are currently being prepared.
Planned outputs:
compartments by change type
changed area by type
before → after status transitions
confidence distribution
Statistics will be added after the final analysis is completed.

## Technology

ArcGIS Pro
ArcGIS Maps SDK for JavaScript
GeoJSON
Cloud Optimized GeoTIFF
HTML / CSS / JavaScript

