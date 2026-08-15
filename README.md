# Rotorua-Forest-Compartment-Change-Mapping-Web-GIS-Viewer

An end-to-end forestry GIS project using LINZ multi-temporal aerial imagery, ArcGIS Pro and ArcGIS Maps SDK for JavaScript to review forest compartment changes and present the results in an interactive before/after Web GIS viewer.

## Final Output

<img width="2545" height="1347" alt="image" src="https://github.com/user-attachments/assets/71964922-cf15-42f2-97dd-0a47c153df25" />

*Figure 1. Interactive forestry change viewer showing multi-temporal aerial imagery, forest compartment boundaries, selected-compartment highlighting, and attribute information.*

## Project Overview
Two aerial imagery periods were compared:

- **Historical imagery:** 2015–2017 ([Bay of Plenty 0.25m Rural Aerial Photos (2015–2017)](...))
- **Recent imagery:** 2024–2025 ([Bay of Plenty West 0.2m Rural Aerial Photos (2024–2025)](...))

A Rotorua study area containing **38 forest compartments** was reviewed and updated based on visible forestry and land-cover changes.
<img width="2062" height="1153" alt="image" src="https://github.com/user-attachments/assets/20daa3af-5f8a-4bff-9bef-728e19c565db" />
*Figure 2. Rotorua study area and forest compartments reviewed in this project.*

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

*Figure 3. Forest compartment review in ArcGIS Pro using recent aerial imagery to assess compartment condition, boundaries, and associated attributes.*

### 3. Forest Condition Update & QA/QC

Forest compartment boundaries, conditions and attributes were reviewed using the 2015–2017 and 2024–2025 aerial imagery. Geometry, topology and attribute consistency were then checked before the updated layer was prepared for Web GIS use.

#### Example 1 — Young Plantation to Established Forest Canopy

<table> <tr> <td align="center"><b>2015–2017</b></td> <td align="center"><b>2024–2025</b></td> </tr> <tr> <td width="50%"> <img width="100%" alt="Historical aerial imagery 2015-2017" src="https://github.com/user-attachments/assets/e5751a31-2fed-44b5-ac03-6aaf4e129e6d" /> </td> <td width="50%"> <img width="100%" alt="Recent aerial imagery 2024-2025" src="https://github.com/user-attachments/assets/1276955e-ffaa-48fc-8694-17f91422725b" /> </td> </tr> </table>

*Figure 4. Plantation growth from recently established young trees in 2015–2017 to a dense, established forest canopy by 2024–2025.*

**Comparison:** The 2015–2017 imagery shows a recently planted compartment with young, sparsely established trees. By 2024–2025, the same area had developed into a dense and continuous plantation canopy, indicating substantial forest growth over the period.

#### Example 2 — Established Forest to Harvested Clear-cut

<table> <tr> <td align="center"><b>2015–2017</b></td> <td align="center"><b>2024–2025</b></td> </tr> <tr> <td width="50%"> <img width="100%" alt="Historical compartment condition 2015-2017" src="https://github.com/user-attachments/assets/168e52f6-9aaa-4887-b3ed-d6aaec32cfd4" /> </td> <td width="50%"> <img width="100%" alt="Updated compartment condition 2024-2025" src="https://github.com/user-attachments/assets/bba48ac5-a20b-4492-b7d4-412cf50035b8" /> </td> </tr> </table>

*Figure 5. Forest harvesting change from an established plantation canopy in 2015–2017 to a recently clear-cut area in 2024–2025.*

**Comparison:** The 2015–2017 imagery shows an established forest canopy, while the 2024–2025 imagery shows the compartment largely clear-cut, with exposed ground and scattered felled logs still visible across the harvested area.

#### Example 3 - Harvested Land to Established Plantation Forest

<table> <tr> <td align="center"><b>2015–2017</b></td> <td align="center"><b>2024–2025</b></td> </tr> <tr> <td width="50%"> <img width="100%" alt="Historical aerial imagery 2015-2017" src="https://github.com/user-attachments/assets/fe781337-4256-4ff8-9105-86fa540f42ff" /> </td> <td width="50%"> <img width="100%" alt="Recent aerial imagery 2024-2025" src="https://github.com/user-attachments/assets/b05b1a48-c2ba-4474-871a-7b25b5ccbcca" /> </td> </tr> </table>

*Figure 6. Forest regeneration from post-harvest bare ground in 2015–2017 to an established plantation forest by 2024–2025.*

**Comparison:** The 2015–2017 imagery shows a recently harvested compartment dominated by exposed ground with little established tree cover. By 2024–2025, the area had been replanted and developed into a well-established plantation forest with substantial canopy cover.

### 4. Web GIS
An interactive viewer was developed using ArcGIS Maps SDK for JavaScript.
Key functions include:

- Before / After imagery swipe
- Study-area imagery clipping
- Forest compartment overlay
- Compartment selector
- Automatic zoom
- Selected-feature highlighting
- Fixed attribute popup
  
<img width="1807" height="1116" alt="image" src="https://github.com/user-attachments/assets/c68ae888-1fd9-4921-a166-af019500519a" />

*Figure 7. ArcGIS Web GIS interface combining imagery swipe comparison, forest compartment selection, automatic zoom, selected-feature highlighting, and a fixed attribute popup.*

## Results

### Forest Condition Area Change
The total study area remained approximately 1,483 ha, while the distribution of forest condition changed substantially between the two imagery periods. 
- Standing forest **increased** from 1,022.97 ha to 1,400.17 ha.
- Harvested area **decreased** from 374.10 ha to 74.54 ha.
- Young plantation **decreased** from 85.52 ha to 8.15 ha.
- Open / bare land **decreased** from 0.25 ha to approximately zero.

These changes indicate a strong overall shift toward established standing plantation forest, consistent with forest growth and replanting observed in the multi-temporal aerial imagery.  

<p align="center">
  <img width="700" alt="Forest condition area comparison" src="https://github.com/user-attachments/assets/5e59eee1-bbea-4e55-8c46-9ad15105fa6a" />
</p>

<p align="center">
  <em>Figure 8. Total forest compartment area by condition for the 2015–2017 and 2024–2025 imagery periods.</em>
</p>




## Technology

ArcGIS Pro
ArcGIS Maps SDK for JavaScript
GeoJSON
Cloud Optimized GeoTIFF
HTML / CSS / JavaScript

