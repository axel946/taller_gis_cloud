# Taller de publicación de mapas utilizando herramientas en la nube

## Fuentes de datos

Carpeta

	/datos

**Municipios y departamentos de Colombia**

Fuente:  Geoportal Dane https://geoportal.dane.gov.co/v2/?page=elementoDescargaMGN

* Departamentos : MGN_ADM_MPIO_POLITICO.zip
* Municipios: mgn_adm_mpio_politico_simplified.geojson.zip
* Documento técnico : FICHA_TECNICA_MGN_2016.pdf

**Tweets**

* Tweets Georreferenciados - Colombia entre :   tweets_2018.zip

**Otros**

* Population density across US state (GeoJSON file is borrowed from the Leaflet choropleth tutorial) : stateData.geojson


## Referencias

El presente taller utiliza contenidos basados en recursos como los siguientes:
* Mapbox
	* Mapbox Studio Manual https://www.mapbox.com/help/studio-manual/
	* Make a choropleth map, Part 1: create a style  https://www.mapbox.com/help/choropleth-studio-gl-pt-1/
* Carto
	* Carto documentation https://carto.com/docs/


## Mapbox


### Cartogram

	"instantly make a map from a photo."

https://www.mapbox.com/cartogram/#11.05/4.622/-74.1774

Imagen de Ejemplo:

![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/Van_Gogh_-_Starry_Night_-_Google_Art_Project.jpg/300px-Van_Gogh_-_Starry_Night_-_Google_Art_Project.jpg)

Resultado:

![cartogram](/images/cartogram.png)

Utilizar Estilo

![cartogram](/images/cartogram_list.png)


Ejemplo:
https://api.mapbox.com/styles/v1/gkudos/cjeaqkalvk2i82slc4rrnjri8.html?fresh=true&title=true&access_token=pk.eyJ1IjoiZ2t1ZG9zIiwiYSI6IkJ6Snd0WVUifQ.KkZKDrLUGoAuDv8CfLg4xg#13.0/40.720538/-73.997072/0


## Spatial SQL

### Postgis

		PostGIS is an extension to the PostgreSQL object-relational database system which allows
		GIS (Geographic Information Systems) objects to be stored in the database. PostGIS
		includes support for GiST-based R-Tree spatial indexes, and functions for analysis
		and processing of GIS objects.

Referencia de operaciones en postgis:
http://www.postgis.org/docs/reference.html




### Simplificación de Geometrías

ST_Simplify:  http://www.postgis.org/docs/ST_Simplify.html  

Datos sin Simplificar:

![municipios](/images/municipios_original.png)

Simplificación de Geometrías:

		SELECT st_simplify(the_geom, 0.001), mpio_cnmbr, mpio_ccnct
		FROM mgn_adm_mpio_politico

Datos Simplificados:

![municipios](/images/municipios_simplicada.png)

Datos Simplificados (Detalle):

![municipios](/images/municipios_simplificada_Detalle.png)

Comparación de Tamaños:

![municipios](/images/municipios_comparacion.png)
