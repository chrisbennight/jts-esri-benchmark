based on: http://svn.osgeo.org/osgeo/foss4g/benchmarking/geometry_libraries/comparisons/jts/

## To Prepare:
Download one of the tiger census counties file - I tested against the first (2 April 2013) one here
http://www.nws.noaa.gov/geodata/catalog/county/html/county.htm

Extract all the files to a directory and edit the file location in the GeomBenchmark main method to point to the shp file you extracted



## To Run:
mvn clean compile
mvn exec:exec
