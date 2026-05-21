# Reflection Questions
## 1. What role does PostGIS play in this architecture? 
### PostGIS is the database that stores all the spatial data like parcels and roads. It keeps both the location and the attribute information of each feature. It also allows spatial functions like converting data into GeoJSON so it can be used by web applications. In this laboratory, Flask connects to PostGIS to get the data, so PostGIS acts as the main source of all spatial information in the system.
