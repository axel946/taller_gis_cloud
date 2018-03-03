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

* Tweets Georreferenciados en Colombia recopilados del  19 al 28 de febrero de 2018 :   tweets_2018.zip

**Otros**

* Population density across US state (GeoJSON file is borrowed from the Leaflet choropleth tutorial) : stateData.geojson


## Referencias

El presente taller utiliza contenidos basados en recursos como los siguientes:
* Mapbox
	* Mapbox Studio Manual https://www.mapbox.com/help/studio-manual/
	* Make a choropleth map, Part 1: create a style  https://www.mapbox.com/help/choropleth-studio-gl-pt-1/
* Carto
	* Carto documentation https://carto.com/docs/
	* Carto Guides https://carto.com/learn/guides/
	* Carto Tips https://carto.com/docs/tips-and-tricks/




## Mapbox


### Cartogram

	"instantly make a map from a photo."

https://www.mapbox.com/cartogram/#11.05/4.622/-74.1774

**Imagen de Ejemplo:**

![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/Van_Gogh_-_Starry_Night_-_Google_Art_Project.jpg/300px-Van_Gogh_-_Starry_Night_-_Google_Art_Project.jpg)

Resultado:

![cartogram](/images/cartogram.png)


Utilizar Estilo

![cartogram](/images/cartogram_list.png)


Ejemplo:

https://api.mapbox.com/styles/v1/gkudos/cjeaqkalvk2i82slc4rrnjri8.html?fresh=true&title=true&access_token=pk.eyJ1IjoiZ2t1ZG9zIiwiYSI6IkJ6Snd0WVUifQ.KkZKDrLUGoAuDv8CfLg4xg#13.0/40.720538/-73.997072/0

**Ejemplo de uso con mapbox gl:**

https://bl.ocks.org/dersteppenwolf/cd1c72c482ed72cfcf8156ad65ef3e26


**Ejemplo de uso con leaflet:**

https://bl.ocks.org/dersteppenwolf/e87dccd027e28208ca955047b08b2537



**Ejemplo de uso en QGIS con WMTS**


![cartogram](/images/mapbox_qgis0.png)

![cartogram](/images/mapbox_qgis1.png)

![cartogram](/images/mapbox_qgis2.png)

![cartogram](/images/mapbox_qgis3.png)

![cartogram](/images/mapbox_qgis4.png)


### Personalizar estilos con Mapbox studio

![cartogram](/images/mapbox_custom.png)

![cartogram](/images/mapbox_custom2.png)


### Mapa de coropletas (choropleth)  con Mapbox studio

De wikipedia:

	Un mapa coroplético, mapa coropleto o mapa de coropletas, es un mapa temático en el que las regiones
	se colorean de un motivo que muestra una medida estadística, como puede ser la densidad de población
	o el ingreso por habitante. Este tipo de mapa facilita la comparación de una medida estadística
	de una región con la de otra o muestra la variabilidad de esta para una región dada.

**Ejemplo:**

![municipios](http://gisgeography.com/wp-content/uploads/2016/07/All-Classes-Map-678x304.png)



**Referencia:**

* Sugerencias de colores para mapas : "Colorbrewer" http://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3
* Choropleth Maps – A Guide to Data Classification http://gisgeography.com/choropleth-maps-data-classification/


**Pasos**

* Datos: datos/stateData.geojson
* Tutorial : "Make a choropleth map, Part 1: create a style" https://www.mapbox.com/help/choropleth-studio-gl-pt-1/

Resultado

![municipios](/images/choropleth-1520047366401.png)


### Otros Tutoriales

*  https://www.mapbox.com/help/tutorials/


## Carto

**Datos:**

* Tweets Georreferenciados en Colombia recopilados del  19 al 28 de febrero de 2018 :   tweets_2018.zip

![municipios](/images/tweets.png)


Ejemplo de la información contenida en el tweet:

	datos/tweet.geojson


* Departamentos : MGN_ADM_MPIO_POLITICO.zip

![municipios](/images/depto.png)

* Municipios: mgn_adm_mpio_politico_simplified.geojson.zip

![municipios](/images/muni.png)


**Pasos**

* Explorar la interfaz de carto

** Carto Editor Workflow https://carto.com/docs/carto-editor/workflow/
** Carto Dashboard https://carto.com/docs/carto-editor/dashboard/
** Galería de mapas de ejemplo https://carto.com/gallery/



* Cargar datos en Carto

* Visualizar estructura de dataset

![municipios](/images/depto_tabla.png)


** Tip: Arquitectura de Carto **

![municipios](/images/carto_architecture.png)

![municipios](/images/carto_how.png)



## Spatial SQL

### Postgis

		PostGIS is an extension to the PostgreSQL object-relational database system which allows
		GIS (Geographic Information Systems) objects to be stored in the database. PostGIS
		includes support for GiST-based R-Tree spatial indexes, and functions for analysis
		and processing of GIS objects.

**Referencia de operaciones en postgis:**

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
