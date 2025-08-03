# California Wildfire Fund (CWF) - GIS Data Science Repository

## Project Overview

This repository hosts the GIS data and related documentation for the Sedgwick Forensic Accounting Services (FAS) Data Science team's work on the California Wildfire Fund project. The California Wildfire Fund, established under California Public Utilities Code section 3284, provides a mechanism for reimbursing utility companies for wildfire-related claims when those claims exceed specified threshold amounts.

Sedgwick serves as the claims administrator for the California Wildfire Fund, working in collaboration with the California Earthquake Authority, the state of California, and major utility companies including Pacific Gas & Electric (PG&E), San Diego Gas & Electric (SDG&E), and Southern California Edison (SoCal Edison). This repository supports the data science aspects of claims administration through advanced geospatial analytics and mapping capabilities.

## Data Privacy and Security Notice

**IMPORTANT**: All data hosted in this public repository consists exclusively of publicly available geographic information system (GIS) data. No confidential claim information, personal identifiable information (PII), or proprietary Sedgwick data is stored in this repository. All confidential claims data is processed through secure, private systems in accordance with Sedgwick's data security protocols and California Wildfire Fund administrative procedures.

## GIS Data Components

This repository contains geospatial datasets essential for wildfire claims analysis and geographic risk assessment:

### Wildfire Perimeter Data
- **Source**: National Interagency Fire Center (NIFC) and CAL FIRE
- **Content**: Precise geographic boundaries of wildfire burn areas
- **Format**: GeoJSON and Shapefile formats
- **Coordinate System**: WGS84 (EPSG:4326)
- **Usage**: Primary dataset for determining proximity of claims to wildfire perimeters and assessing geographic impact zones

### NIFC Wildfire Perimeter Data
The National Interagency Fire Center provides authoritative wildfire perimeter data that serves as the foundational geographic reference for claims analysis. This data includes:
- Final fire perimeters for completed wildfire incidents
- Daily progression perimeters for active fires (when available)
- Historical fire perimeter data for trend analysis
- Metadata including fire names, incident dates, acreage, and containment status

### NMS SMOKE and FIRE Data
The NOAA National Meteorological Service SMOKE and FIRE datasets provide atmospheric and environmental context for wildfire events:
- **SMOKE Data**: Atmospheric smoke concentration and dispersion modeling
- **FIRE Data**: Active fire detection from satellite imagery
- **Temporal Resolution**: Real-time and historical data
- **Applications**: Air quality impact assessment, evacuation zone analysis, and secondary damage evaluation

### AVA Viticultural Area Perimeter Data
American Viticultural Area (AVA) boundaries are critical for assessing agricultural losses in California's wine regions:
- **Source**: TTB (Alcohol and Tobacco Tax and Trade Bureau)
- **Content**: Official boundaries of designated wine growing regions
- **Relevance**: Essential for evaluating crop losses, terroir impacts, and agricultural business interruption claims
- **Format**: Polygon shapefiles with detailed boundary information

### Additional Geographic Reference Data
- County boundaries and administrative divisions
- Census tract and block group data for demographic analysis
- Transportation networks and infrastructure layers
- Elevation and topographic data for fire behavior modeling
- Weather station locations and historical meteorological data

## California Wildfire Fund Claims Mapping Tool

### Overview
The FAS Data Science team has developed sophisticated R Shiny web applications that integrate these GIS datasets with claims data to provide interactive geographic analysis capabilities. These tools enable claims adjusters, forensic accountants, and subject matter experts to:

1. **Visualize Claim Locations**: Plot individual claims on interactive maps with precise coordinates
2. **Assess Fire Proximity**: Calculate exact distances from claim locations to wildfire perimeters
3. **Analyze Geographic Risk**: Evaluate claims within the context of multiple environmental and geographic factors
4. **Generate Spatial Reports**: Produce detailed geographic analyses for individual claims or claim portfolios

### Core Functionalities
- **Address Geocoding**: Convert claim addresses to precise latitude/longitude coordinates using Google Maps API
- **Distance Calculations**: Compute shortest distances from claim locations to fire perimeters using advanced geometric algorithms
- **Interactive Mapping**: Provide pan/zoom capabilities with multiple data layers and real-time analysis
- **Export Capabilities**: Generate high-resolution map exports and data downloads for reporting purposes

### Technical Architecture
The mapping tools are built using:
- **R Shiny**: Web application framework providing interactive user interfaces
- **Leaflet**: JavaScript mapping library for dynamic, mobile-friendly maps
- **sf Package**: Simple features package for advanced spatial data operations
- **Google Maps API**: Geocoding services for address resolution
- **Security Framework**: Microsoft Forms and Lists integration for secure data handling

## Covered Wildfire Events

### Kincade Fire (2019)
**Event Summary**: The Kincade Fire was a major wildfire that occurred in Sonoma County, California, from October 23 to November 6, 2019. The fire was ignited during a period of extreme weather conditions, including powerful Diablo winds and critically dry vegetation conditions.

**Geographic Impact**:
- **Total Acreage Burned**: 77,758 acres (314.4 square kilometers)
- **Primary Counties Affected**: Sonoma County (primary), Lake County (secondary)
- **Communities Impacted**: Geyserville, Healdsburg, Windsor, and surrounding unincorporated areas
- **Structures**: 374 structures destroyed, including 174 single-family residences

**Claims Analysis Context**:
- **Agricultural Losses**: Significant impact on Sonoma County wine industry, affecting multiple AVAs
- **Residential Claims**: Predominantly rural and suburban properties in fire-prone areas
- **Business Interruption**: Tourism and agricultural business disruptions throughout Sonoma County
- **Infrastructure**: Power line infrastructure involvement requiring detailed investigation

### Dixie Fire (2021)
**Event Summary**: The Dixie Fire was the largest single wildfire in California history, burning from July 13 to October 25, 2021. The fire complex ultimately burned across five counties in Northern California, creating unprecedented challenges for claims administration and geographic analysis.

**Geographic Impact**:
- **Total Acreage Burned**: 963,309 acres (3,898.8 square kilometers)
- **Primary Counties Affected**: Butte, Plumas, Lassen, Shasta, and Tehama Counties
- **Communities Impacted**: Greenville, Canyon Dam, Clear Creek, and numerous rural communities
- **Structures**: 1,329 structures destroyed, including 688 single-family residences

**Claims Analysis Context**:
- **Scale Complexity**: Massive geographic footprint requiring sophisticated spatial analysis tools
- **Rural Property Challenges**: Remote property locations creating geocoding and valuation complexities
- **Diverse Property Types**: Mix of residential, commercial, agricultural, and recreational properties
- **Extended Duration**: Multi-month fire progression requiring temporal analysis capabilities

**Technical Challenges**:
- **Data Volume**: Extensive perimeter data requiring optimized processing algorithms
- **Coordinate Precision**: Rural addresses often lacking precise coordinates necessitating enhanced geocoding
- **Multi-County Analysis**: Cross-jurisdictional claims requiring standardized geographic references

## R Shiny Application Integration

### Data Linking and Permalinks
The GIS data stored in this repository is directly integrated into the R Shiny mapping applications through stable permalink references. The applications access data using specific GitHub raw URLs that provide reliable, version-controlled access to the geographic datasets.

### Example Implementation
```r
# Example permalink integration for Dixie Fire perimeter data
wildfire_perimeter_url <- "https://raw.githubusercontent.com/[repository-path]/Dixie_Fire_Perimeter_AF02.geojson"
geojson_data <- st_read(wildfire_perimeter_url)
```

### Version Control and Data Updates
All GIS datasets are version-controlled through Git, ensuring that applications can reference specific versions of geographic data. This approach provides:
- **Reproducible Analysis**: Consistent geographic references across time
- **Data Integrity**: Immutable references for historical analysis
- **Update Management**: Controlled deployment of updated geographic data

## Technical Specifications

### Data Formats
- **Primary Format**: GeoJSON (RFC 7946 compliant)
- **Secondary Formats**: ESRI Shapefiles, KML, and GPX where applicable
- **Coordinate Reference System**: WGS84 (EPSG:4326) for all datasets
- **Encoding**: UTF-8 for all text and attribute data

### Quality Assurance
All geographic data undergoes quality assurance processes including:
- **Geometric Validation**: Verification of polygon topology and coordinate accuracy
- **Attribute Verification**: Cross-reference with authoritative sources
- **Temporal Consistency**: Validation of date/time metadata
- **Projection Verification**: Confirmation of coordinate system accuracy

### File Organization
```
/data
  /wildfire_perimeters
    /kincade
    /dixie
    /[additional_fires]
  /boundaries
    /ava_viticultural
    /counties
    /administrative
  /environmental
    /nms_smoke
    /nms_fire
    /weather_stations
  /infrastructure
    /transportation
    /utilities
    /emergency_services
```

## Research and Development Applications

### Statistical Sampling Integration
The GIS data supports Sedgwick's statistical sampling methodologies by providing geographic stratification capabilities. Claims can be sampled based on:
- **Distance from Fire Perimeter**: Stratified sampling by proximity zones
- **Geographic Clustering**: Spatial clustering analysis for representative sampling
- **Property Type Distribution**: Geographic distribution of different property classifications

### Predictive Analytics
The comprehensive geographic datasets enable development of predictive models for:
- **Risk Assessment**: Pre-event vulnerability analysis based on historical fire patterns
- **Claims Volume Forecasting**: Geographic prediction of potential claim concentrations
- **Loss Estimation**: Spatial modeling of potential loss severities

### Machine Learning Applications
The structured GIS data provides training datasets for machine learning applications including:
- **Automated Damage Assessment**: Computer vision analysis of post-fire satellite imagery
- **Geographic Pattern Recognition**: Identification of high-risk geographic patterns
- **Claim Classification**: Automated categorization based on geographic characteristics

## Usage Instructions for R Shiny Applications

### Prerequisites
To utilize the GIS data with R Shiny applications, ensure the following dependencies are installed:

```r
# Required R packages
install.packages(c(
  "shiny", "leaflet", "sf", "ggmap", "shinythemes",
  "leaflet.extras", "DT", "plotly", "shinycssloaders"
))
```

### Basic Implementation Example
```r
library(shiny)
library(leaflet)
library(sf)

# Load wildfire perimeter data from repository
fire_data <- st_read("https://raw.githubusercontent.com/[repo-path]/fire_perimeter.geojson")

# Create basic Shiny app with fire perimeter overlay
ui <- fluidPage(
  titlePanel("Wildfire Claims Mapping"),
  leafletOutput("map")
)

server <- function(input, output) {
  output$map <- renderLeaflet({
    leaflet() %>%
      addTiles() %>%
      addPolygons(data = fire_data, 
                  color = "red", 
                  fillOpacity = 0.3,
                  popup = ~fire_name)
  })
}

shinyApp(ui = ui, server = server)
```

### Advanced Spatial Analysis
For more sophisticated analysis capabilities, the data can be integrated with advanced spatial functions:

```r
# Calculate distance from point to fire perimeter
calculate_fire_distance <- function(claim_coords, fire_polygon) {
  claim_point <- st_as_sf(claim_coords, coords = c("lon", "lat"), crs = 4326)
  distance_meters <- st_distance(claim_point, fire_polygon)
  return(as.numeric(distance_meters))
}

# Spatial intersection analysis
assess_fire_impact <- function(property_polygon, fire_polygon) {
  intersection <- st_intersection(property_polygon, fire_polygon)
  impact_percentage <- st_area(intersection) / st_area(property_polygon)
  return(as.numeric(impact_percentage))
}
```

## Data Sources and Attribution

### Primary Data Sources
- **National Interagency Fire Center (NIFC)**: Wildfire perimeter data
- **CAL FIRE**: California wildfire incident data and perimeters
- **NOAA National Weather Service**: Meteorological and atmospheric data
- **TTB**: American Viticultural Area boundaries
- **U.S. Census Bureau**: Administrative boundaries and demographic data
- **USGS**: Topographic and elevation data

### Data Licensing and Usage Rights
All geographic data hosted in this repository is either:
1. **Public Domain**: Government datasets available for unrestricted use
2. **Open Source**: Data available under open licensing terms
3. **Attributed Sources**: Data requiring proper attribution (all attributions provided)

### Update Schedule
- **Wildfire Perimeters**: Updated as new incidents occur and final perimeters are published
- **Administrative Boundaries**: Updated annually or as jurisdictional changes occur
- **Environmental Data**: Updated based on source agency publication schedules
- **Infrastructure Data**: Updated quarterly or as significant changes are identified

## Contact and Support

### Technical Support
For technical questions regarding the GIS data or R Shiny applications:
- **Email**: CWFsupport@sedgwick.com
- **Project Lead**: Antonio Figueroa, VP Claims Data Science
- **Organization**: Sedgwick Forensic Accounting Services

### Data Issues and Corrections
To report data quality issues or request corrections:
1. Create an issue in this GitHub repository
2. Include specific geographic coordinates or identifiers
3. Provide detailed description of the issue
4. Include supporting documentation when available

## Future Development

### Planned Enhancements
- **Expanded Fire Coverage**: Addition of historical California wildfire perimeters
- **Enhanced Weather Data**: Integration of real-time weather station data
- **Improved Resolution**: Higher precision geographic boundaries where available
- **Additional Layers**: Incorporation of vegetation, soil, and hydrologic data

### Open Source Transition
The FAS Data Science team is evaluating the transition of select R Shiny applications to open source availability. This would include:
- **Educational Applications**: Tools for academic research and education
- **Public Benefit Tools**: Applications supporting community wildfire preparedness
- **Industry Standards**: Contributions to open industry standards for wildfire claims analysis

## Contributing

### Data Contributions
We welcome contributions of additional high-quality geographic datasets relevant to wildfire claims analysis. Contributors should:
1. Ensure data meets quality standards outlined in this documentation
2. Provide comprehensive metadata and source attribution
3. Verify compatibility with existing coordinate systems and formats
4. Submit data through pull request with detailed documentation

### Code Contributions
For contributions to R Shiny applications or data processing scripts:
1. Follow established coding standards and documentation practices
2. Include comprehensive testing for new functionality
3. Ensure compatibility with existing security and data privacy requirements
4. Provide clear documentation of new features or modifications

## License

This repository is licensed under the terms specified in the LICENSE file. The licensing applies specifically to the arrangement and presentation of the data, while individual datasets retain their original licensing terms as specified by their respective source agencies.

---

**Disclaimer**: This repository contains geographic data for research and analysis purposes. The data should not be used as the sole basis for emergency planning, evacuation decisions, or other safety-critical applications. Always consult official sources and local authorities for current wildfire information and safety guidance.