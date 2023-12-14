Geospatial impact of blackouts from winter storms in Houston, Texas

This repository contains an analysis of the impact of winter storms in February 2021 on the Houston metropolitan area. In this analysis, we investigate the geospatial extent of power outages caused by the storms and investigate whether socioeconomic attributes are correlated. .

The structure and contents of the repository are shown below:

    geospatial-analysis-2021-houston-blackouts
    │   README.md                               
    │   2021_houston_blackouts.Rmd file        #analysis markdown file
    │   2021_houston_blackouts.html file       #analysis HTML file
    │
    └───data/
        │   gis_osm_buildings_a_free_1.gpkg    #geospatial data on buildings from Open Street Map, downloaded from [Geofabrik](https://download.geofabrik.de/)
        │   gis_osm_roads_free_1.gpkg          #geospatial data on roads from Open Street Map, downloaded from [Geofabrik](https://download.geofabrik.de/)
        │
        └───ACS_2019_5YR_TRACT_48_TEXAS.gdb    #geospatial socioeconomic data for census tracts in 2019, downloaded from the [U.S. Census Bureau's American Community Survey](https://www.census.gov/programs-surveys/acs)
        |   │   census tract gdb files         #geometries are stored in the `ACS_2019_5YR_TRACT_48_TEXAS` layer and income data is stored in the `X19_INCOME` layer
        |
        └───VNP46A1
        |   │   VIIRS data files               #satellite images of night lights from the Visible Infrared Imaging Radiometer Suite (VIIRS) of the Suomi satellite, downloaded from NASA's [Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)](https://ladsweb.modaps.eosdis.nasa.gov/)

Data

The data used in this analysis are too large to include in the repository and instead can be downloaded from [here](https://drive.google.com/file/d/1bTk62xwOzBqWmmT791SbYbHxnCdjmBtw/view?usp=sharing). Descriptions of the data sources are shown below:


*Night lights* 
We utilized remotely-sensed nighttime radiance data sourced from the [Visible Infrared Imaging Radiometer Suite (VIIRS)](https://en.wikipedia.org/wiki/Visible_Infrared_Imaging_Radiometer_Suite) onboard the Suomi satellite. We utilize the VNP46A1 product in particular, which includes daily, top-of-atmosphere, at-sensor nighttime radiance. The VNP46A1 data were downloaded from NASA's [Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)](https://ladsweb.modaps.eosdis.nasa.gov/) and prepared before this analysis. The VIIRS data are distributed in 10x10 degree tiles in sinusoidal equal-area projection. Each tile can be identified by its horizontal and vertical position in the grid. Since Houston is located on the border of tiles h08v05 and h08v06, we use two tiles for each date included in the analysis. After exploring the data around the 2021 winter storms through NASA's Worldview, we decided to use VIIRS data from 2021-02-07 and 2021-02-16 because they provide clear images comapared to other dates with too much cloud cover. The data are stored in the `VNP46A1` sub-folder and are as follows:

-   `VNP46A1.A2021038.h08v05.001.2021039064328.h5.tif`: tile h08v05, collected on 2021-02-07  

-   `VNP46A1.A2021038.h08v06.001.2021039064329.h5.tif`: tile h08v06, collected on 2021-02-07  

-   `VNP46A1.A2021047.h08v05.001.2021048091106.h5.tif`: tile h08v05, collected on 2021-02-16  

-   `VNP46A1.A2021047.h08v06.001.2021048091105.h5.tif`: tile h08v06, collected on 2021-02-16  


*Roads*
We utilized geospatial data of the roads that are located within the Houston metropolitan area. The source of these data was [OpenStreetMap (OSM)](https://planet.openstreetmap.org/), which is a collaborative project that creates publicly available geographic data. We downloaded data on all Texas highways from [Geofabrik](https://download.geofabrik.de/), a third-party company that redistributes OSM data, and prepared a GeoPackage with a subset of roads in the Houston metropolitan area before this analysis. These data are stored in the following file: 

- `gis_osm_roads_free_1.gpkg`


*Homes*
We utilized geospatial data of the buildings that are located within the Houston metropolitan area. The source of these data was also [OpenStreetMap (OSM)](https://planet.openstreetmap.org/). We downloaded the data for Texas and perpared a GeoPackage with homes in the Houston metropolitan area before this analysis. These data are stored in the following file: 

- `gis_osm_buildings_a_free_1.gpkg`

*Socioeconomic attributes*
We utilized socioeconomic data at the census tracts level from the 2019 [U.S. Census Bureau's American Community Survey](https://www.census.gov/programs-surveys/acs). The data are formatted in an ArcGIS ["file geodatabase"](https://desktop.arcgis.com/en/arcmap/latest/manage-data/administer-file-gdbs/file-geodatabases.htm), which is a multi-file proprietary format that's similar to a GeoPackage file. Each layer in the ArcGIS file geodatabase contains a subset of the fields document in the [ACS metadata](https://www2.census.gov/geo/docs/maps-data/data/tiger/prejoined/ACSMetadata2011.txt). The geometry information is separate from the ACS layers and is combined in our analysis. These data are stored in the following folder:

-`ACS_2019_5YR_TRACT_48.gdb`

### Results

Two summary figures from the analysis are shown below: ![Alt Text]()

