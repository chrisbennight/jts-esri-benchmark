based on: http://svn.osgeo.org/osgeo/foss4g/benchmarking/geometry_libraries/comparisons/jts/

## To Prepare:
Download one of the tiger census counties file - I tested against the first (2 April 2013) one here
http://www.nws.noaa.gov/geodata/catalog/county/html/county.htm

Extract all the files to a directory and edit the file location in the GeomBenchmark main method to point to the shp file you extracted



## To Run:
mvn clean compile
mvn exec:exec


## Output
(I think I must be doing something wrong with the intersection operator) - this is on a i7 920.

<pre>
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building geom-performance-check 0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- exec-maven-plugin:1.2.1:exec (default-cli) @ geom-performance-check ---
Reading content c_02ap13
Total Area730.0445917511596

JTS AREA: 2803 total: 730.0445917511627 other: 0 time: 0.064901718 s
ESRI AREA: 2803 total: 730.0445917511674 other: 0 time: 0.127963648 s

JTS CENTROID: 2803 total: -91.60642950541535 other: 38.08915874601412 time: 0.271346335 s
ESRI - UNSUPPORTED CENTROID: -1 total: 0.1 other: 0.1 time: -1.0E-9 s

JTS HULL: 2803 total: 822.4889226894925 other: 0 time: 0.594456502 s
ESRI HULL: 2803 total: 822.4889226894913 other: 0 time: 1.34728754 s

JTS INTERSECTION: 101 total: 158.5542576517085 other: 730.0445917511596 time: 7.394382941 s
ESRI INTERSECTION: 101 total: 158.55425765345527 other: 730.0445917511589 time: 26.016691411 s

JTS CLIP: 2803 total: 370.1493045493162 other: 730.0445917511596 time: 1.118819886 s
ESRI CLIP: 2803 total: 370.14930454931573 other: 730.0445917511589 time: 0.521066555 s

JTS SIMPLIFY: 2803 total: 6197.906981556354 other: 6213.17050681722 time: 0.781470335 s
ESRI SIMPLIFY: 2803 total: 6213.17050681722 other: 6213.17050681722 time: 5.176590418 s

JTS WITHIN: 2803 total: 2796 other: -1 time: 0.990175033 s
ESRI WITHIN: 2803 total: 2796 other: -1 time: 0.482023383 s

JTS CONTAINS: 2803 total: 2761 other: -1 time: 0.2525412 s
ESRI CONTAINS: 2803 total: 2761 other: -1 time: 0.065102861 s
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 58.617s
[INFO] Finished at: Thu Jun 06 21:05:49 EDT 2013
[INFO] Final Memory: 5M/183M
[INFO] ------------------------------------------------------------------------
</pre>
