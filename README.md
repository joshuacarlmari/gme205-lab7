# Reflection Questions

## 1. What role does PostGIS play in this architecture? 
### PostGIS is the database that stores all the spatial data like parcels and roads. It keeps both the location and the attribute information of each feature. It also allows spatial functions like converting data into GeoJSON so it can be used by web applications. In this laboratory, Flask connects to PostGIS to get the data, so PostGIS acts as the main source of all spatial information in the system.
## 2. What role does Flask play in this laboratory?
### Flask acts as the web service layer in this laboratory. It connects to the PostGIS database, retrieves the spatial data using SQL queries, and then converts the results into GeoJSON format. Flask also creates REST API endpoints like /api/parcels and /api/roads so that clients such as a web browser or QGIS can access the data through HTTP requests. In short, Flask is responsible for delivering the spatial data from the database to the GIS clients.

## 3. Why is GeoJSON useful for spatial web services? 
### GeoJSON is useful for spatial web services because it is a simple, lightweight format for representing geographic data using standard JSON. It can store both points, lines, polygons and attribute information in a way that is easy for web applications and GIS tools like QGIS to read. Since it is text-based, it can be easily transferred over the internet through REST APIs without needing complex file formats like shapefiles. This makes GeoJSON ideal for sharing and displaying spatial data in web and client-server GIS systems.

## 4. How does ST_AsGeoJSON() support distributed GIS? 
### `ST_AsGeoJSON()` supports distributed GIS by converting spatial data stored in PostGIS geometries into GeoJSON format that can be easily shared over the web. This allows the data to be accessed remotely through REST APIs instead of requiring direct access to the database. As a result, different clients like QGIS, web maps, or other applications can consume the same spatial data over HTTP. This makes the system more flexible and enables spatial data to be used across multiple platforms in a distributed environment.

## 5. Why is QGIS considered a heavy client?
### QGIS is considered a heavy client because it is a full-featured desktop GIS application that performs most processing on the user’s computer instead of relying on a server. It can handle large datasets, perform spatial analysis, editing, styling, and visualization locally. Unlike lightweight web clients, QGIS requires installation and more system resources such as memory and processing power. This makes it powerful but also more resource-intensive compared to browser-based GIS applications.


## 6. Why is a REST API better than manually exporting shapefiles?
### A REST API is better than manually exporting shapefiles because it provides real-time access to spatial data without needing to repeatedly export and transfer files. With a REST API, data is always up to date since it is directly retrieved from the PostGIS database. It also allows multiple clients like QGIS or web applications to access the same data at the same time through HTTP requests. Unlike shapefiles, which are static and need manual updates, a REST API makes the system more efficient, scalable, and easier to manage.

## 7. How does this laboratory demonstrate distributed geospatial computing?
### This laboratory demonstrates distributed geospatial computing by showing how spatial data is stored, processed, and accessed across different systems. The data is stored in PostGIS, processed and served through a Flask REST API, and then consumed by clients like QGIS over HTTP. Instead of keeping everything in one application, the workload is distributed between the database server, the web service, and the GIS client. This setup allows multiple users and applications to access the same spatial data remotely, showing how modern GIS systems operate in a networked and distributed environment.

## 8. What advantages does service-based GIS architecture provide?
### Service-based GIS architecture provides several advantages because it separates data storage, processing, and visualization into different components connected through a web service. It improves efficiency since data can be accessed directly from the database through APIs without manual file handling. It also ensures that all users and applications access the most updated version of the data in real time. In addition, it supports multiple clients like QGIS and web applications at the same time, making the system more scalable, flexible, and easier to maintain.


## 9. How does this architecture support scalability in spatial systems?
### This architecture supports scalability because it separates the system into independent components: PostGIS for storage, Flask for data services, and QGIS or web clients for access. Each layer can be upgraded or expanded without affecting the others. For example, the database can handle more data, the API can serve more requests, and multiple clients can connect at the same time through HTTP. This makes it easier to support more users, larger datasets, and additional services without redesigning the whole system.
