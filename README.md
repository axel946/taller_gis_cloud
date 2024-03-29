# Taller de publicación de mapas utilizando herramientas en la nube

- [Taller de publicación de mapas utilizando herramientas en la nube](#taller-de-publicaci%C3%B3n-de-mapas-utilizando-herramientas-en-la-nube)
	- [Instructor](#instructor)
	- [Prerrequisitos](#prerrequisitos)
	- [Fuentes de datos](#fuentes-de-datos)
	- [Referencias](#referencias)
	- [Mapbox](#mapbox)
		- [Cartogram](#cartogram)
		- [Personalizar estilos con Mapbox studio](#personalizar-estilos-con-mapbox-studio)
		- [Mapa de coropletas (choropleth) con Mapbox studio](#mapa-de-coropletas-choropleth-con-mapbox-studio)
		- [Otros Tutoriales](#otros-tutoriales)
	- [Carto](#carto)
		- [Ejercicio 1: Mapa Simple de tweets](#ejercicio-1-mapa-simple-de-tweets)
		- [Ejercicio 2: Crear dashboard interactivo para el análisis de tweets](#ejercicio-2-crear-dashboard-interactivo-para-el-an%C3%A1lisis-de-tweets)
		- [Ejercicio 3: Agregaciones / Densidad](#ejercicio-3-agregaciones--densidad)
		- [Ejercicio 4: Mapa de coropletas (choropleth)](#ejercicio-4-mapa-de-coropletas-choropleth)
		- [Ejercicio 5: Análisis espacial básico](#ejercicio-5-an%C3%A1lisis-espacial-b%C3%A1sico)
		- [Ejercicio 6: Enriquecer los datos con Análisis espacial](#ejercicio-6-enriquecer-los-datos-con-an%C3%A1lisis-espacial)
	- [Carto y Spatial SQL](#carto-y-spatial-sql)
		- [Postgis](#postgis)
		- [Consultas utilizando SQL](#consultas-utilizando-sql)
		- [Simplificación de Geometrías](#simplificaci%C3%B3n-de-geometr%C3%ADas)
- [Gracias](#gracias)


## Instructor
 
* Juan Carlos Méndez

## Prerrequisitos

Tener cuenta en los siguientes servicios en la nube:

* Mapbox
* Carto
* Wordpress
* Github

## Fuentes de datos

Carpeta

	/datos

** Municipios y departamentos de Colombia**

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

* Wordpress
	* Tutorial paso a paso de wordpress https://learn.wordpress.com/
	* Build a Business Website Tutorial https://en.support.wordpress.com/tutorials/business-website-tutorial/
	* Video Tutorials »Get Started – Learn the Basics https://en.support.wordpress.com/video-tutorials/get-started/
	* Video Tutorials »Customize Your Site https://en.support.wordpress.com/video-tutorials/customize-your-site/
	* Video Tutorials »Add Content and Media https://en.support.wordpress.com/video-tutorials/add-content-and-media/
	* Video Tutorials »Integrate and Connect to Social Media https://en.support.wordpress.com/video-tutorials/connect-to-social-media/
	* Carto embeds https://en.support.wordpress.com/carto-embeds/
	* Video Publicar entradas en Wordpress https://en.support.wordpress.com/carto-embeds/

* Ejemplos de historias contadas con Mapas
	* The Impact of Brooklyn's L Train Shutdown, in 4 Maps https://www.citylab.com/transportation/2016/07/the-impact-of-nycs-l-train-shutdown-in-4-maps/493115/
	* The L Train Closure—what Data Can Tell Us https://carto.com/blog/looking-at-the-l/
	* 12 Maps That Tell the Story of 2017 https://carto.com/blog/maps-tell-the-story-2017/
	* Immigration. Le Centre-Bretagne à contresens http://www.letelegramme.fr/dataspot/immigration-le-centre-bretagne-a-contresens-20-04-2016-11037935.php#EuBizhJQ4bA6IPlj.99
	* Anti-eviction Mapping Project and Carto Expose Realities of Gentrification and Evictions in San Francisco https://carto.com/blog/anti-eviction-mapping/
	* Mapping City Data Shows Link Between Redlining and Foreclosures https://carto.com/blog/mapping-city-data-shows-link-between-redlining-and-foreclosures/
	* Exploring real-time hurricane evacuation patterns https://blog.mapbox.com/exploring-real-time-hurricane-evacuation-patterns-d7a6199f77db
	* Global Warming with a Flourish http://googlemapsmania.blogspot.com.co/2018/03/global-warming-with-flourish.html
	* Who owns England? http://googlemapsmania.blogspot.com.co/2018/02/who-owns-england.html
	* Where can you afford to rent in California? http://www.latimes.com/projects/la-fi-california-rental-affordable-map/
	* Strava’s fitness heatmaps are a 'potential catastrophe' https://www.engadget.com/2018/02/02/strava-s-fitness-heatmaps-are-a-potential-catastrophe/
	* Mapped: the best places to live in England and Wales https://www.telegraph.co.uk/finance/economics/11041812/Mapped-the-best-places-to-live-in-England-and-Wales.html
	* America's Wall. http://www.kpbs.org/news/2017/nov/13/americas-wall/#explore






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

![cartogram](/images/density.png)

### Ejercicio 4: Mapa de coropletas (choropleth)

* Cargue en carto el conjunto de datos stateData.geojson
* cree un mapa a partir de esos datos
* Simbolícelo por densidad y compare diferentes formas de clasificaciòn y rampas de color
* Adicione las etiquetas utilizando el atributo name
* explore la opción "cartocss" y revise el código generado por la herramienta
* publique el mapa
* resultado: https://gkudos.carto.com/u/kudosg/builder/ae9352da-4ad4-4941-9273-d04bf52ddda5/embed

![cartogram](/images/choro.png)


### Ejercicio 5: Análisis espacial básico

Objetivo: Crear un mapa de municipios clasificado por la cantidad de tweets

* Cree  un nuevo mapa y adicione las capas de tweets y municipio
* seleccione la capa de municipios.
* Seleccione la opción de análisis :  "Intersect and Aggregate" ( https://carto.com/help/building-maps/intersect-and-aggregate/ )
	* capa de intersección :  tweets
	* medida: conteo
* Simbolice los municipios como coropletas  a partir del conteo de tweets
* adicione los widgets que considere necesarios para enriquecer la visualización
* resultado https://gkudos.carto.com/u/kudosg/builder/ecdf1d43-7d19-4c60-9b61-c20683818a00/embed

![cartogram](/images/choro2.png)


### Ejercicio 6: Enriquecer los datos con Análisis espacial

Objetivo: Adicionar atributos a los datos a partir de procesos de análisis espacial

* Cree  un nuevo mapa y adicione la capas de departamentos
* Adicione el análisis de tipo "Select Points in Polygons" (https://carto.com/help/building-maps/select-points-in-polygons/) utilizando como filtering layer los tweets
* Adicione widget de categoría por el atributo _nombre_
* Adicine widget para conteo de datos a través del atributo source_cartodb_id
* publique el mapa
* pregunta: cuantos tweets hay en total entre antioquia y cundinarca
* resultado https://gkudos.carto.com/u/kudosg/builder/fb040332-80ec-4a91-8599-d08a69b07f8a/embed

![cartogram](/images/enrichment.png)


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


**Nota:**
	* Agrupar puntos en polígonos (convex hull) https://carto.com/learn/guides/analysis/group-points-into-polygons/


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


# Gracias
