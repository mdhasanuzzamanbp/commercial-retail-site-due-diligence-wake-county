# Commercial Retail Development — Preliminary Site Due Diligence & Conceptual Site Plan Wake County, North Carolina, USA 

# Executive Summary
The project visualizes a GIS-based screening to identify potentially suitable parcels for commercial retail development. The analysis combines an initial screening (zoning, land use, parcel size), site constraints (Flood, Wetland, Creek), and an accessibility assessment (Roads), which produced final priority outputs

The initial screening process is followed:  

- 59 GB/HC (commercial zoning areas) zoning regions from 355 regions
- 226 GB/HC zoning-intersected parcels were identified from 437582 Parcels
- 41 parcels were identified that were equal to or greater than 8 acres
- 22 parcels were selected for constraint and accessibility assessment as per classification  (Agriculture, Vacant, or Horticulture)
- Secondary screening was performed with flood exposure, wetland constraints, creek proximity, and road access
- A Weighted Multi-Criteria Evaluation (MCE) was applied to combine the screening criteria and candidate parcel ranking
- 4 final candidate parcels were identified as suitable for commercial retail development

# Objectives

The primary objective of this analysis is to identify and prioritize potentially suitable parcels for commercial retail development using a structured GIS-based site-selection methodology.

The analysis is designed to answer three key questions:

1. Are the parcels located within potentially suitable GB/HC commercial zoning areas?
2. Which parcels meet the minimum size (8 acres) and land-use (Agriculture, Vacant, or Horticulture) requirements?
3. Which candidate parcels have the most favorable combination of accessibility and environmental conditions?

# Project Workflow

<p align="center">
<img width="auto" height="760" alt="Picture1" src="https://github.com/user-attachments/assets/9f8febc7-5259-480e-8a9a-22089da49db7" />
</p>

# Tools

QGIS: Select by location, select by expression, Statistics by categories, fix geometries, reproject, aggregate, intersect, dissolve
Microsoft Excel: Data Analysis
Microsoft Word: Documentation

# Data source

### Table 1: Data Sources Table

| Data | Source | Purpose |
|---|---|---|
| **Zoning** | [Wake County Zoning — Data.gov](https://catalog.data.gov/dataset/wake-county-zoning) | Identify GB/HC zoning areas |
| **Parcels** | [Wake County Parcels — Data.gov](https://catalog.data.gov/dataset/parcels-d1495) | Parcel boundaries, area, and land-use screening |
| **Flood Hazard** | [FEMA National Flood Hazard Layer (NFHL)](https://www.fema.gov/flood-maps/national-flood-hazard-layer) | Identify parcels affected by mapped flood hazards |
| **Wetlands** | [U.S. Fish & Wildlife Service — National Wetlands Inventory (NWI)](https://www.fws.gov/program/national-wetlands-inventory/download-state-wetlands-data) | Identify mapped wetland constraints |
| **Creeks / Streams** | [USGS National Hydrography — Data Access](https://www.usgs.gov/national-hydrography/access-national-hydrography-products) | Identify streams/creeks and create the 500-ft buffer |
| **Roads** | [Wake County Streets — Data.gov](https://catalog.data.gov/dataset/streets-in-wake-county-nc) | Evaluate road class, speed, and accessibility |

# Results & Discussions
## 1. Initial Screening
First, parcels were screened based on zoning, parcel size, and existing land-use characteristics to select final parcels for the next analysis. This step consists of 4 screening stages:  Zoning Screening, Parcel Selection, Parcel Size and Land-Use Screening.

<p align="center">
<img width="4724" height="3779" alt="01  GIS-based parcel screening workflow for commercial site selection" src="https://github.com/user-attachments/assets/b7df5918-3989-4fd9-8e65-f477590b69c1" />
</p>

Fig: GIS-based parcel initial screening workflow for commercial site selection. (Top Left) Zoning Screening (Top Right) Parcel Intersection (Bottom Left) Parcel Size Screening (Bottom Right) Land-Use Screening

### 1.1 Zoning Screening
The first stage focused on identifying GB/HC zoning areas considered relevant to the commercial retail site-selection objective. A total of 59 GB/HC zoning polygons were identified for the initial screening from 355 zoning regions. These zoning areas were selected to identify the potentially suitable parcels.

### 1.2 Parcel Selection
The selected 59 GB/HC zoning polygons were spatially compared with the original parcel datasets. This process identified 226 parcels intersecting the selected GB/HC zoning areas from 437582 parcels.

### 1.3 Parcel Size
The 226 intersecting parcels were screened using a minimum parcel-size threshold of 8 acres. Following this screening, 41 parcels met the minimum size requirement. This step removes smaller properties that may be less suitable for the intended commercial retail development scenario.

### 1.4 Land-Use Screening
The 41 parcels were subsequently screened according to their existing land-use classifications.
Parcels were retained according to the following classifications:

- Agriculture 
- Vacant 
- Horticulture
  
After screening, 22 candidate parcels were finally selected for environmental constraints analysis and accessibility assessment.

## 2. Site Constraints and Accessibility Assessment

With the results of initial screening, the 22 final candidate parcels were evaluated for environmental constraints and transportation accessibility.
Four assessment categories were considered to identify the most suitable parcels as follows:
- Creek proximity
- Flood hazard 
- Wetland conditions 
- Road access

This stage was designed to distinguish candidate parcels with more favorable site conditions from those affected by environmental or accessibility constraints.

<p align="center">
<img width="4133" height="4074" alt="02  Site Constraints   Accessibility Assessment" src="https://github.com/user-attachments/assets/56ac32d3-8146-48f6-8aec-02b234b13f76" />
</p>

Fig: Environmental Site Constraints (Creek, Flood, Wetland) & Accessibility Assessment (Roads) workflow

### 2.1 Creek Screening
Creek and stream proximity was assessed by creating a 500-ft buffer around the relevant creek/stream features. Candidate parcels that were located outside the 500-ft buffer were classified as Creek-Safe parcels, which gives more flexibility to select suitable parcels with strict criteria. Candidate parcels located within or intersecting the 500-ft buffer were classified as Creek-Risk.

### 2.2 Flood Screening
Candidate parcels were then evaluated against the mapped FEMA flood hazard area. Parcels that were outside the mapped flood hazard area were classified as Flood-Safe for this screening criterion. On the other hand, intersected parcels with the mapped hazard area were classified as Flood-Risk. No additional buffer was applied to the FEMA flood hazard area in this analysis.

### 2.3 Wetland Screening
The candidate parcels were also evaluated against mapped wetland areas. Parcels without an identified wetland intersection were classified as Wetland-Safe, while parcels intersecting mapped wetlands were classified as Wetland-Affected.

### 2.4 Road Accessibility Screening

Road accessibility was evaluated using characteristics of the surrounding road network.
The assessment incorporated:
- Road class (State and City road classification) 
- Road speed 

The resulting road-access assessment was incorporated into the overall site suitability evaluation. The first priority was to select the parcels who has state road access. When there is no state road access in that case speed was considered the second priority.

## 3. Weighted Multi-Criteria Evaluation

<p align="justify">
Following the individual constraint and access assessments, the 22 candidate parcels were evaluated using a Weighted Multi-Criteria Evaluation (MCE). The purpose of the MCE was to combine the individual screening criteria into a single comparative suitability assessment. Each criterion was converted into a score representing its relative suitability. The individual scores were then combined using the predetermined criterion weights to calculate a Weighted Score for each candidate parcel.
</p>

The equation is as follows:
Weighted Score = Σ (Criterion Score × Criterion Weight)

The MCE values for each criterion are given below:

## Table 2: Weighted Multi-Criteria Evaluation (MCE)

| Criterion | Assessment Factor | Scoring | Weight |
|---|---|---|---:|
| 🏞️ **Creek** | 500-ft creek buffer | Outside buffer = higher score | 15% |
| 🌊 **Flood** | FEMA flood hazard exposure | Flood-safe = higher score | 30% |
| 🌿 **Wetland** | Wetland intersection | Wetland-safe = higher score | 30% |
| 🛣️ **Road Access** | Road class & speed | Higher accessibility = higher score | 25% |
| **Total** | — | — | **100%** |

The resulting weighted scores were used to establish the relative priority of the candidate parcels.

## Table 3: Final Priority Ranking — 22 Candidate Parcels

| Rank | Parcel ID | Area (acres) | Land Use | Creek | Road | Flood | Wetland | Total Score | Weighted Score | Priority | Township | Year Built |
|---:|---:|---:|---|---:|---:|---:|---:|---:|---:|---|---|---:|
| 1 | 126729 | 15.76 | Agriculture | 1 | 1 | 1 | 1 | 4 | **100** | **Very High** | Mark's Creek | 1951 |
| 2 | 295568 | 11.15 | Vacant | 1 | 1 | 1 | 1 | 4 | **100** | **Very High** | Mark's Creek | — |
| 3 | 198435 | 17.43 | Agriculture | 0 | 1 | 1 | 1 | 3 | **85** | **High** | Little River | 1940 |
| 4 | 320113 | 10.56 | Agriculture | 1 | 0 | 1 | 1 | 3 | **75** | **High** | Panther Branch | 1920 |
| 5 | 20269 | 11.97 | Agriculture | 0 | 0 | 1 | 1 | 2 | **60** | **Moderate** | Little River | — |
| 6 | 124975 | 8.98 | Agriculture | 0 | 0 | 1 | 1 | 2 | **60** | **Moderate** | Panther Branch | — |
| 7 | 278021 | 100.65 | Agriculture | 0 | 1 | 1 | 0 | 2 | **55** | **Moderate** | St. Matthew's | 1920 |
| 8 | 82044 | 54.58 | Agriculture | 0 | 1 | 1 | 0 | 2 | **55** | **Moderate** | Panther Branch | 1935 |
| 9 | 102139 | 38.24 | Agriculture | 0 | 1 | 1 | 0 | 2 | **55** | **Moderate** | Swift Creek | 1944 |
| 10 | 211263 | 14.35 | Agriculture | 0 | 1 | 1 | 0 | 2 | **55** | **Moderate** | Middle Creek | 1940 |
| 11 | 408624 | 30.07 | Agriculture | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | Little River | 1930 |
| 12 | 165121 | 24.26 | Agriculture | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | Mark's Creek | — |
| 13 | 282250 | 20.46 | Agriculture | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | Middle Creek | — |
| 14 | 210439 | 15.87 | Agriculture | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | White Oak | 2014 |
| 15 | 213841 | 12.81 | Vacant | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | Wake Forest | — |
| 16 | 10917 | 11.00 | Agriculture | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | White Oak | 1997 |
| 17 | 311260 | 10.95 | Vacant | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | Mark's Creek | — |
| 18 | 408908 | 8.53 | Horticulture | 0 | 0 | 1 | 0 | 1 | **30** | **Low** | Panther Branch | 1999 |
| 19 | 237496 | 57.26 | Agriculture | 0 | 1 | 0 | 0 | 1 | **25** | **Low** | Mark's Creek | 1992 |
| 20 | 296878 | 159.19 | Agriculture | 0 | 0 | 0 | 0 | 0 | **0** | **Low** | Middle Creek | 1925 |
| 21 | 359104 | 20.22 | Agriculture | 0 | 0 | 0 | 0 | 0 | **0** | **Low** | Middle Creek | 1924 |
| 22 | 15918 | 14.73 | Vacant | 0 | 0 | 0 | 0 | 0 | **0** | **Low** | Mark's Creek | — |

## 4. High Priority Parcels Selection
The weighted scores were used to establish the final priority ranking of candidate parcels. Higher scores indicate a more favorable combination of the evaluated site characteristics, while lower scores indicate comparatively greater constraints or less favorable accessibility. After evaluation, finally, 4 candidate parcels were selected as high priority for commercial site development.
<p align="center">
<img width="2834" height="3248" alt="03  Commercial Retail Site Selection — Final Priority Sites" src="https://github.com/user-attachments/assets/ff6bbfd5-afea-4da5-b790-dd7381b9426c" />
</p>
Figure 4. Final high priority candidate parcels based on the weighted multi-criteria evaluation (MCE).

## Table 4: Top 4 High Priority Parcels 

| Rank | Parcel ID | Area (acres) | Land Use | Creek Score | Road Score | Flood Safe | Wetland Score | Total Score | Weighted Score | Priority |
|---:|---:|---:|---|---:|---:|---:|---:|---:|---:|---|
| 1 | 126729 | 15.76 | Agriculture | 1 | 1 | 1 | 1 | 4 | 100 | **Very High** |
| 2 | 295568 | 11.15 | Vacant | 1 | 1 | 1 | 1 | 4 | 100 | **Very High** |
| 3 | 198435 | 17.43 | Agriculture | 0 | 1 | 1 | 1 | 3 | 85 | **High** |
| 4 | 320113 | 10.56 | Agriculture | 1 | 0 | 1 | 1 | 3 | 75 | **High** |

## QA/QC

Before spatial analysis, datasets were reprojected to a consistent coordinate reference system EPSG: 2264, and invalid geometries were corrected using the Fix Geometries tool. Spatial indexes were created to improve spatial processing efficiency. Spatial overlay results, candidate classifications, MCE weights, final scores, rankings, and map outputs were also reviewed for clarity and consistency.

## Recommendations
The GIS analysis identifies parcels that appear relatively favorable based on the selected screening criteria. The highest-ranked sites should therefore be considered priority candidates for further due diligence.
For next-step project development, several criteria should be verified. In case the high-priority sites have further limitations, priority will be given to the following priority parcels according to the rankings.

The determining criteria are:
- Development and infrastructure costs 
- Utility availability and capacity 
- Property ownership and availability 
- Topography and drainage 
- Local planning and development regulations

The GIS analysis should therefore be considered a screening and decision-support tool, rather than a substitute for property-level engineering, environmental, legal, or regulatory due diligence.

## Limitations

Mapped wetlands and flood-hazard areas in GIS should be treated as screening information rather than substitutes for field verification or regulatory determinations. Similarly, road-access scoring provides a comparative assessment of accessibility based on the available road characteristics but does not establish legal access, driveway approval, traffic capacity, or transportation permitting.
For final decision, field assessment is necessary to consider other factors such as cost, utility, drainage, etc. for long-term planning.
