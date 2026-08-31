# Commercial Retail Development — Preliminary Site Due Diligence & Conceptual Site Plan Wake County, North Carolina, USA 

# Executive Summary
The project visualizes a GIS-based screening to identify potentially suitable parcels for commercial retail development. The analysis combines an initial screening (zoning, land use, parcel size), site constraints (Flood, Wetland, Creek), and an accessibility assessment (Roads), which produced final priority outputs

The initial screening process is followed:  

- 59 GB/HC (commercial zoning areas) zoning regions from 355 regions
- 226 GB/HC zoning intersected parcels were identified from 437582 Parcels
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

<img width="auto" height="600" alt="Picture1" src="https://github.com/user-attachments/assets/c72a94c9-4642-496a-a421-dffeb585e2ea" />

# Tools

QGIS: Select by location, select by expression, Statistics by categories, fix geometries, reproject, aggregate, intersect, dissolve

# Data source

## Data Sources

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

### 1.1 Zoning Screening
The first stage focused on identifying GB/HC zoning areas considered relevant to the commercial retail site-selection objective. A total of 59 GB/HC zoning polygons were identified for the initial screening from 355 zoning regions. These zoning areas were selected to identify the potentially suitable parcels.

### 1.2 Parcel Intersection
The selected 59 GB/HC zoning polygons were spatially compared with the original parcel datasets. This process identified 226 parcels intersecting the selected GB/HC zoning areas from 437582 parcels.

### 1.3 Minimum Parcel Size
The 226 intersecting parcels were screened using a minimum parcel-size threshold of 8 acres. Following this screening, 41 parcels met the minimum size requirement. This step removes smaller properties that may be less suitable for the intended commercial retail development scenario.

### 1.4 Existing Land-Use Screening
The 41 parcels were subsequently screened according to their existing land-use classifications.
Parcels were retained according whop meets the following classifications:
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

### 2.1 Creek Screening
Creek and stream proximity was assessed by creating a 500-ft buffer around the relevant creek/stream features.
Candidate parcels that were located outside the 500-ft buffer were classified as Creek-Safe parcels, which gives more flexibility to select suitable parcels with strict criteria.
Candidate parcels located within or intersecting the 500-ft buffer were classified as Creek-Risk.


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
Following the individual constraint and access assessments, the 22 candidate parcels were evaluated using a Weighted Multi-Criteria Evaluation (MCE).
The purpose of the MCE was to combine the individual screening criteria into a single comparative suitability assessment.

Each criterion was converted into a score representing its relative suitability. The individual scores were then combined using the predetermined criterion weights to calculate a Weighted Score for each candidate
parcel.

The equation is as follows:
Weighted Score = Σ (Criterion Score × Criterion Weight)

The MCE values for each criteria is given below:

## Weighted Multi-Criteria Evaluation (MCE)

| Criterion | Assessment Factor | Scoring | Weight |
|---|---|---|---:|
| 🏞️ **Creek** | 500-ft creek buffer | Outside buffer = higher score | 15% |
| 🌊 **Flood** | FEMA flood hazard exposure | Flood-safe = higher score | 30% |
| 🌿 **Wetland** | Wetland intersection | Wetland-safe = higher score | 30% |
| 🛣️ **Road Access** | Road class & speed | Higher accessibility = higher score | 25% |
| **Total** | — | — | **100%** |

The resulting weighted scores were used to establish the relative priority of the candidate parcels.

## 4. Final Priority Ranking
The weighted scores were used to establish the final priority ranking of candidate parcels. Higher scores indicate a more favorable combination of the evaluated site characteristics, while lower scores indicate comparatively greater constraints or less favorable accessibility. After evaluation, finally, 4 candidate parcels were selected as high priority for commercial site development.

Figure 4. Final priority ranking of candidate parcels based on the weighted multi-criteria evaluation.
Final ranking table

8. Recommendations
The GIS analysis identifies parcels that appear relatively favorable based on the selected screening criteria. The highest-ranked sites should therefore be considered priority candidates for further due diligence.
For next-step project development several criteria should be verified. In case, the high priority sites have further limitation priory will be given to the following priority parcels according to the rankings.

The determining criteria are:
- Development and infrastructure costs 
- Utility availability and capacity 
- Property ownership and availability 
- Topography and drainage 
- Local planning and development regulations

The GIS analysis should therefore be considered a screening and decision-support tool, rather than a substitute for property-level engineering, environmental, legal, or regulatory due diligence.

Limitations
Mapped wetlands and flood-hazard areas in GIS should be treated as screening information rather than substitutes for field verification or regulatory determinations. Similarly, road-access scoring provides a comparative assessment of accessibility based on the available road characteristics but does not establish legal access, driveway approval, traffic capacity, or transportation permitting.
For final decision, field assessment is necessary to consider other factors such as cost, utility, drainage etc. for long term planning.

QA/QC

Before spatial analysis, datasets were reprojected to a consistent coordinate reference system EPSG: 2264, and invalid geometries were corrected using the Fix Geometries tool. Spatial indexes were created to improve spatial processing efficiency. Spatial overlay results, candidate classifications, MCE weights, final scores, rankings, and map outputs were also reviewed for clarity and consistency.


