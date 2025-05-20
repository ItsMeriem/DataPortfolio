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


# Methodology

# How to use

