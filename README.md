# plexus-route-builder
Builds GTFS files and GeoJSON file of Metro Manila, Philippines from the mongoDB database of Plexus found in thesis-plexus.herokuapp.com

<b>Building GTFS from Exsiting MongoDB Database</b>

 - Using <i>gtfs-builder.py</i>, run the following methods to pull the route database from Plexus MongoDB store.

<i>build_gtfs([db_connection], [directory_folder])</i>
 - calls <b>builders([to_directory])</b>, creating GTFS txt files in directory folder.
 
            -  build_agency(db,to_directory, "agency.txt")
            -  build_calendar(db,to_directory, "calendar.txt")
            -  build_feed_info(db,to_directory, "feed_info.txt")
            -  build_frequencies(db,to_directory, "frequencies.txt")
            -  build_routes(db,to_directory, "routes.txt")
            -  build_shapes(db,to_directory, "shapes.txt")
            -  build_stop_times(db,to_directory, "stop_times.txt")
            -  build_stops(db,to_directory, "stops.txt")
            -  build_trips(db,to_directory, "trips.txt")
 
 <b>Saving Options from Exsiting MongoDB Database</b>
 
  - Using <i>save-as.py</i>, run the following methods to convert database collection from Plexus MongoDB store to either GeoJSON or Shapefile
  
  <i>save_as_geojson([filename], [geojson_object], test=True)</i>
  - exports as GeoJSON file
  
  <i>save_as_shapefile([geojson_file])</i>
  - converts GeoJSON and exports it to Shapefile
  
  For Revisions: 
  - Directly get geojson object inside save_as_geojson. 
  - Allow user to save/convert database contents as shapefile without supplying an exisiting geojson file.

<b>Versions</b>
 - Version 1.0.0 (08/14/17)
   - Manual cleaning. 60 percent off road per route
 - Version 2.0.0 (09/21/17)
   - Cleaned version. 100 percent on road
 - Version 2.1.0 (10/7/2017)
   - Recalibrated version. Instead of Origin and Destination, Middle waypoint is considered. 100 percent on road.
