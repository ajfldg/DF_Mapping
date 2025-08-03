# Sedgwick Forensic Accounting Services - GIS Data Science Repository

## Project Overview


## Data Privacy and Security Notice

**IMPORTANT**: All data hosted in this public repository consists exclusively of publicly available geographic information system (GIS) data. No confidential claim information, personal identifiable information (PII), or proprietary Sedgwick data is stored in this repository. All confidential claims data is processed through secure, private systems in accordance with Sedgwick's data security protocols and client project procedures.

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

### Overview
The FAS Data Science team has developed sophisticated R Shiny web applications that integrate these GIS datasets with claims data to provide interactive geographic analysis capabilities. These tools enable claims adjusters, forensic accountants, and subject matter experts to examine claims.


### Technical Architecture
The mapping tools are built using:
- **R Shiny**: Web application framework providing interactive user interfaces
- **Google Maps API**: Geocoding services for address resolution

## R Shiny Application Integration

### Data Linking and Permalinks
The GIS data stored in this repository is directly integrated into the R Shiny mapping applications through stable permalink references. The applications access data using specific GitHub raw URLs that provide reliable, version-controlled access to the geographic datasets.


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


## File Organization


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


### Open Source Transition
The FAS Data Science team is evaluating the transition of select R Shiny applications to open source availability. This would include:
- **Educational Applications**: Tools for academic research and education
- **Public Benefit Tools**: Applications supporting community wildfire preparedness
- **Industry Standards**: Contributions to open industry standards for wildfire claims analysis

## Contributing

### Data Contributions


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