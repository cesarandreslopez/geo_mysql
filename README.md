# geo_mysql
geonames.org data dumps into a MySQL database in a Docker container

This is a docker repository that contains a MYSQL with a downloaded Geonames ready for importation on startup.
(http://download.geonames.org/export/dump/readme.txt)
(http://www.geonames.org/)
(http://codigofuerte.github.io/GeoNames-MySQL-DataImport/)

# Please note.
geonames_importer.sh will be executed on startup of the docker container, so mysql will NOT be available at first run until the entire import is completed. This can take around 20 - 25 minutes in total.

# On Docker hub: (change "password" for whatever you want)
docker pull cesarandreslopez/geo_mysql
docker run --name geo_mysql -e MYSQL_ROOT_PASSWORD=password -d cesarandreslopez/geo_mysql

# To self build:

git clone https://github.com/cesarandreslopez/geo_mysql/
## build the geo-mysql-server
docker build -t cesarandreslopez/geo_mysql .

## run the server (change "password" for whatever you want)
docker run --name geo_mysql -e MYSQL_ROOT_PASSWORD=password -d cesarandreslopez/geo_mysql
