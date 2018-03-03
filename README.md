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
	* Carto Editor Workflow https://carto.com/docs/carto-editor/workflow/
	* Carto Dashboard https://carto.com/docs/carto-editor/dashboard/
	* Galería de mapas de ejemplo https://carto.com/gallery/



* Cargar datos en Carto

* Visualizar estructura de dataset

![municipios](/images/depto_tabla.png)


**Tip: Arquitectura de Carto**

![municipios](/images/carto_architecture.png)

![municipios](/images/carto_how.png)


### Ejercicio 1: Mapa Simple de tweets

* Crear un mapa con los datos de los tweets

* Cambiar el mapa base: Comparar las siguientes opciones
	* Voyager
	* Positron
	* Dark Matter
	* Stamen Toner
	* Here Day
	* Nasa

* Adicionar el estilo que creó en mapbox como mapa base de carto

* cambiar el color, transparencia , tamaño y borde de los puntos de los tweets

* personalice el "pop-up" y la leyenda

* habilite el selector de Capa

* cambie la privacidad del mapa a "only accesible with link"

* publique el mapa

* Resultado

https://gkudos.carto.com/u/kudosg/builder/f7f21768-c27a-40ad-88d8-38ab19c6af12/embed

![municipios](/images/carto_primero.png)



* Publique un artículo en su blog de wordpress utilizando el mapa creado con carto
(Nota: Adicione el texto , títulos, etiquetas, etc que considere necesarios para contextualizar el ejercicio )

![municipios](/images/wordpress.png)



* Resultado  

https://neogeografia.wordpress.com/2018/03/02/taller-de-sig-utilizando-herramientas-en-la-nube/

![municipios](/images/wordpress_resultado.png)


### Ejercicio 2: Crear dashboard interactivo para el análisis de  tweets

* Cree un nuevo mapa en carto a partir de los datos de los tweets

* Adicione widget de línea de tiempo utilizando el atributo created  
	* Cambie la agregación de datos (buckets) a horas
	* Explore la línea de tiempo seleccionando un rango específico de tiempo (Ejm: 10 horas)
	* cambie el color
* Adicione widget de formula de tipo  "feature count" para contar los datos que salen en pantalla
	* personalice el nombre, prefijo, sufijo y descripción según como considere necesario
* Adicione widget de categoría con e atributo "source" (aplicación desde la cual se creó el tweet )
* Repita el proceso de la categoría para los atributos lang, screen_name y place name
* cambie los colores del los puntos del tweet según como considere necesario
* personalice el pop-up de la capa de tweets    
		* click: todos los atributos
		* hover: nombre del usuario  y el texto  del tweet
* adicione la capa de departamentos, ubíquela por debajo de los tweets y cambie la simbología
* cambie la privacidad del mapa a "only accesible with link"
* publique el mapa
* explore los datos en el dashboard publicado haciendo diferentes combinaciones
* cree una nueva entrada en su blog de wordpress incluyendo el dashboard creado e incluya sus opiniones sobre el proceso.
	* Le pareciò fácil? difícil?
	* que particulares percibió de los datos luego del análisis interactivo?  
	* este tipo de dashboards serían útiles en su trabajo o profesión? ejemplos

Resultado:
https://gkudos.carto.com/u/kudosg/builder/b4fd7e58-379a-4101-9cd9-bad1111c6fc4/embed

![municipios](/images/carto_dashboard.png)


### Ejercicio 3: Agregaciones / Densidad  

* Cree un nuevo mapa en carto a partir de los datos de los tweets y cambie la simbología agregando por cuadros o hexbins
* cambie la simbología según como considere necesario
* publique el mapa
* resultado : https://gkudos.carto.com/u/kudosg/builder/63e02f53-fd37-43cd-a35a-74bcd00047d9/embed

### Ejercicio 4: Mapa de coropletas (choropleth)

* Cargue en carto el conjunto de datos stateData.geojson
* cree un mapa a partir de esos datos
* Simbolícelo por densidad y compare diferentes formas de clasificaciòn y rampas de color
* Adicione las etiquetas utilizando el atributo name
* explore la opción "cartocss" y revise el código generado por la herramienta
* publique el mapa
* resultado: https://gkudos.carto.com/u/kudosg/builder/ae9352da-4ad4-4941-9273-d04bf52ddda5/embed

### Ejercicio 5: Análisis espacial básico

* Cree  un nuevo mapa y adicione las capas de tweets y municipio
* seleccione la capa de municipios.
* Seleccione la opción de análisis :  "intersectar segunda capa"
	* capa de intersección :  tweets
	* medida: conteo
* Simbolice los municipios como coropletas  a partir del conteo de tweets
* adicione los widgets que considere necesarios para enriquecer la visualización
* resultado https://gkudos.carto.com/u/kudosg/builder/ecdf1d43-7d19-4c60-9b61-c20683818a00/embed


### Ejercicio 6: Enriquecer los datos con Análisis espacial

* Cree  un nuevo mapa y adicione la capas de departamentos
* Adicione el análisis de tipo "filter point in polygons" utilizando como filtering layer los tweets
* Adicione widget de categoría por el atributo source_dpto_cnmbr
* Adicine widget para conteo de datos a través del atributo source_cartodb_id
* publique el mapa
* pregunta: cuantos tweets hay en total entre antioquia y cundinarca
* resultado https://gkudos.carto.com/u/kudosg/builder/13ae268b-4410-4396-bc0c-b31d473b9c55/embed




## Carto y Spatial SQL

### Postgis

		PostGIS is an extension to the PostgreSQL object-relational database system which allows
		GIS (Geographic Information Systems) objects to be stored in the database. PostGIS
		includes support for GiST-based R-Tree spatial indexes, and functions for analysis
		and processing of GIS objects.

**Referencia de operaciones en postgis:**

http://www.postgis.org/docs/reference.html

### Consultas utilizando SQL

*  Cuantos municipios tiene antioquia?

```sql
SELECT count(*) FROM mgn_adm_mpio_politico
where dpto_ccdgo = '05'
```

![municipios](/images/sql.png)

* Cuantos tweets se fueron creados con foursquare  en un radio de 2 km alrededor del centro comercial andino ?

```sql
with b as (
		select st_buffer( cdb_latlng(4.666742040, -74.05286452)::geography, 2000) as the_geom
)
select count(t.*)
from tweets_2018 as t , b
where st_intersects(t.the_geom, b.the_geom)
and t.source = 'foursquare'
```

Respuesta: 115

Ejemplo mapa:
https://gkudos.carto.com/u/kudosg/builder/2597eae1-1029-462d-80bd-ce3d3fba2538/embed

![municipios](/images/filter_advanced.png)


### Simplificación de Geometrías

ST_Simplify:  http://www.postgis.org/docs/ST_Simplify.html  

Datos sin Simplificar:

![municipios](/images/municipios_original.png)

Simplificación de Geometrías:

```sql
SELECT st_simplify(the_geom, 0.001), mpio_cnmbr, mpio_ccnct
FROM mgn_adm_mpio_politico
```

Datos Simplificados:

![municipios](/images/municipios_simplicada.png)

Datos Simplificados (Detalle):

![municipios](/images/municipios_simplificada_Detalle.png)

Comparación de Tamaños:

![municipios](/images/municipios_comparacion.png)
