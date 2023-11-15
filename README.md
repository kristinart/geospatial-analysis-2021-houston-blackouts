# geospatial-analysis-2021-houston-blackouts

This repository contains an analysis of the impact of winter storms in February 2021 on the Houston area. In this analysis, I investigate the geospatial impact of electricity blackouts resulting from the storms and the socioeconomic implications of the resulting distribution.

**Note:** the data associated with this analysis are too large to include in the respository and instead can be downloaded from [here](https://drive.google.com/file/d/1bTk62xwOzBqWmmT791SbYbHxnCdjmBtw/view?usp=sharing).

The structure and contents of the repository are:

geospatial-analysis-2021-houston-blackouts
│   README.md
│   2021_houston_blackouts.Rmd file        #analysis markdown file
│   2021_houston_blackouts.html file       #analysis HTML file
│
└───data
    │   gis_osm_buildings_a_free_1.gpkg    #geospatial data on buildings from Open Street Map, downloaded from [Geofabrik](https://download.geofabrik.de/)
    │   gis_osm_roads_free_1.gpkg          #geospatial data on roads from Open Street Map, downloaded from [Geofabrik](https://download.geofabrik.de/)
    │
    └───ACS_2019_5YR_TRACT_48_TEXAS.gdb    #geospatial socioeconomic data for census tracts in 2019, downloaded from the [U.S. Census Bureau's American Community Survey](https://www.census.gov/programs-surveys/acs)
    |   │   census tract gdb files         #geometries are stored in the `ACS_2019_5YR_TRACT_48_TEXAS` layer and income data is stored in the `X19_INCOME` layer
    |
    └───VNP46A1
    |   │   VIIRS data files               #satellite images of night lights from the Visible Infrared Imaging Radiometer Suite (VIIRS) of the Suomi satellite, downloaded from NASA's [Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)](https://ladsweb.modaps.eosdis.nasa.gov/)
