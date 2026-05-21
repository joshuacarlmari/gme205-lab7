# Reflection Questions

## 1. What role does PostGIS play in this architecture? 
### PostGIS is the database that stores all the spatial data like parcels and roads. It keeps both the location and the attribute information of each feature. It also allows spatial functions like converting data into GeoJSON so it can be used by web applications. In this laboratory, Flask connects to PostGIS to get the data, so PostGIS acts as the main source of all spatial information in the system.

## 2. What role does Flask play in this laboratory?
### Flask acts as the web service layer in this laboratory. It connects to the PostGIS database, retrieves the spatial data using SQL queries, and then converts the results into GeoJSON format. Flask is responsible for delivering the spatial data from the database to the GIS clients.

## 3. Why is GeoJSON useful for spatial web services? 
### GeoJSON is useful for spatial web services because it is a simple, lightweight format for representing geographic data using standard JSON. It can store both points, lines, polygons and attribute information in a way that is easy for web applications and GIS tools like QGIS to read. Since it is text-based, it can be easily transferred over the internet through REST APIs without needing complex file formats like shapefiles. This makes GeoJSON ideal for sharing and displaying spatial data in web and client-server GIS systems.

## 4. How does ST_AsGeoJSON() support distributed GIS? 
### `ST_AsGeoJSON()` supports distributed GIS by converting spatial data stored in PostGIS geometries into GeoJSON format that can be easily shared over the web. This makes the data easy to share through APIs, so different clients can access it remotely without needing direct database access. As a result, different clients like QGIS, web maps, or other applications can consume the same spatial data over HTTP. This makes the system more flexible and enables spatial data to be used across multiple platforms in a distributed environment.

## 5. Why is QGIS considered a heavy client?
### QGIS is considered a heavy client because it is a full-featured desktop GIS application that performs most processing on the user’s computer instead of relying on a server. It can handle large datasets, run analyses, and create visualizations, but it needs more memory and processing power compared to lightweight web apps. This makes it powerful but also more resource-intensive compared to browser-based GIS applications.


## 6. Why is a REST API better than manually exporting shapefiles?
### A REST API is better than manually exporting shapefiles because it provides real-time access to spatial data without needing to repeatedly export and transfer files. Data is always up to date since it is directly retrieved from the PostGIS database. It also allows multiple clients like QGIS or web applications to access the same data at the same time through HTTP requests. Shapefiles are static and need to be exported and updated manually. APIs are faster, more efficient, and allow multiple clients to use the same data at once.

## 7. How does this laboratory demonstrate distributed geospatial computing?
### This laboratory demonstrates distributed geospatial computing by showing how spatial data is stored, processed, and accessed across different systems. The data is stored in PostGIS, processed and served through a Flask REST API, and then consumed by clients like QGIS over HTTP. The work is shared between components, allowing remote access and multiple users.


## 8. What advantages does service-based GIS architecture provide?
### Service-based GIS architecture provides several advantages because it separates data storage, processing, and visualization into different components connected through a web service. This makes data access more efficient, ensures everyone sees the latest version, and supports multiple clients at the same time. It is flexible, scalable, and easier to maintain. It also supports multiple clients like QGIS and web applications.


## 9. How does this architecture support scalability in spatial systems?
### This architecture supports scalability because it separates the system into independent components. PostGIS for storage, Flask for data services, and QGIS or web clients for access. Each layer can be upgraded or expanded without affecting the others. This makes it easier to support more users, larger datasets, and additional services without redesigning the whole system.
