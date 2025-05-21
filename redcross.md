<h1 align="center"> Geospatial Modeling of Real Time Earthquake Impacts to Housing </h1>

# Introduction:

For my masters capstone at Carnegie Mellon University, we worked with the American Red Cross to develop a predictive tool of the estimate the number of people expected to seek shelter in the aftermath of an earthquake. This product is **the first open source earthquake model** to provide shelter demand estimates. It is expected to reduce the time needed to deploy life-saving resources by 3 days, ensuring the RC can help people as rapidly as possible.

The American Red Cross plays an important role in disaster response, providing emergency shelter, food, and support services to communities affected by natural disasters. In the event of an  earthquake, one of the most urgent needs is to rapidly assess how many impacted individuals will require public shelter. Currently, the American Red Cross relies on tools like FEMA’s HAZUS models to assess earthquake impacts; however, these tools are technically complex, inflexible, and difficult to operate in urgent, "no-notice" disaster scenarios. Additionally, no existing models provide precise estimates of shelter demand.

To address these limitations, our team developed an open source model to rapidly estimate shelter needs following an earthquake. The tool integrates real-time United 
States Geological Survey (USGS) ShakeMap data to assess earthquake intensity, along with publicly available building stock data and HAZUS-derived damage functions to estimate structural damage. These physical vulnerability assessments are combined with social vulnerability indicators to generate a more accurate estimate of the population likely to seek shelter. The graph below demonstrates our methodology: from earthquake to structural building vulnerability to social vulnerability. Our methodology is designed to be accessible and practical for the American Red Cross analysts, requiring minimal technical expertise and avoiding the need for specialized software.

### ADD IMAGE OF METHODLOGY HERE!

# Data
The data is either automatically downloaded when the code is ran or it is already included in the repo. No additional data downloads are needed. Here's a breakdown of the data used: 

| Data Source | Description | 
|-------|--------|
|USGS Shakemap|ShakeMaps provide near-real-time maps of ground motion and shaking intensity following significant earthquakes. We use the ShakeMap API to search for earthquake information using the earthquake's Event ID. [Link](https://earthquake.usgs.gov/data/shakemap/)|
|Census Tract Geographic Boundaries| Our tool automatically downloads the spatial shapefiles for the geographic boundaries of census tracts and counties|
|The 2020 Decennial Census| We use tract-level population counts from the 2020 Decennial Census. [Link](https://data.census.gov/table/DECENNIALPL2020.P1?t=Populations+and+People&g=040XX00US06$1400000)|
|FEMA USA Structures|The USA Structures geo database has building-level data, indicating the exact spatial location of each building. [Link](https://disasters.geoplatform.gov/USA_Structures/)|
|General Building Stock Data| Tract-level breakdown of structure types. These can either be deriverd through the National Structure Inventory or through the Hazus software|
|HAZUS Damage Function Variables|These are a set of cumulative distribution functions whose variables are dependent on structure type and seismic design code. They provide a framework to estimate the probability that a structure might meet or exceed Slight, Moderate, Extensive, or Complete damage based on the peak ground acceleration (PGA) of the area.|
|Social Vulnerability Index|The Social Vulnerability Index (SVI) is a place-based index designed to identify and quantify communities experiencing social vulnerability. [Link](https://www.atsdr.cdc.gov/place-health/php/svi/index.html)|

# Methodology

To estimate the number of people seeking shelter after an earthquake, we first estimate the structural building damage caused by the disaster (physical vulnerability), then estimate the  habitability of those buildings, and finally the social vulnerability of the residents.
### ADD IMAGE OF METHODLOGY HERE!

Here's a breakdown of each step and the relevant script:

"""
ShakeMap Retrieval and Processing Module

This module provides functions to:
- Fetch earthquake event data from the USGS GeoJSON feed using an event ID
- Parse key event metadata including magnitude, coordinates, depth, and URL
- Download and extract ShakeMap shapefiles (mi, pga, pgv) for qualifying events
- Save relevant metadata in a structured format for further analysis
"""

# How to use

# References
