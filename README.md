# Drainage-Structures-Mapping-Algorithm (DSMA)
Bridges and culverts mapping using ALS point clouds and Road centerline information. 
The following steps are required to use the code/tools provides here.
The DSMA algorithm is comprised of 4 modules to map bridges and culverts. Each module is summerized here
a) Data preparation
  Input data 1. classified ALS point clouds in LAS format. The ground points (class code 2) must be present.
             2. Road centerlines. Road centerlines are available Highways authorities known as Federal Highway Administration (FHWA, USA).For, rest of the world, please find the associated government authorities to acquire road centerlines data. Alternatively, road centerlines can be obtained from OpenStreetMap (OSM) i.e., world open source map platform. The road ceterlines for any region can be dirtectly downloaded from https://www.openstreetmap.org/ in XML (Extended Markup Language) format. XML to shapefile conversion is possible with Esri ArcGIS or with open-source QGIS.
             However, weather goverment or OSM, the road centerlines dataset is subject to completeness i.e., some of the roads might be absent from acquired datasets. e.g. residential streets, private road etc. To include the those roads centerlines that were not available in above mentioned sources, an impervious surface area can either be acquired for can mapped using high resolution satellite/Ortho-images. The ISA can be converted in road centerlines.
Pre-processing: The DSMA input LAS files should be converted in tiles. For that purpose, LidR opensource package is available to convert larger LAS files into smaller tiles of same size. Please visit https://github.com/Jean-Romain/lidR for further details.
Creating a road mask: Please follow the published article associated with DSMA development for the process to create road mask.
b) ALS modified DEM production
   The ALS-mDEM is produced by removing the ALS ground points from each tile using road mask created in previous step. 
