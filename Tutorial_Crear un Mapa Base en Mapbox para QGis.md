> *Si estás aburrido de los mapas base clásicos y quieres darle un toque personal a tus creaciones cartográficas, este sencillo tutorial te mostrará cómo hacerlo :).

## Contexto

Cuando Google abrió su servicio de [mapas](https://www.google.com/maps) en el año 2005 provocó un gran impacto en cuanto a la democratización de la distribución de información espacial, gracias a la sencillez que brinda para la creación de mapas a través de Internet. Por al menos cinco años (mucho tiempo en escala Internet), el formato y la intefaz de google maps se transformó en el estándar para las representaciones cartográficas en la Web, ya que el año 2010 con el lanzamiento de MapBox descubrimos que además de la sencillez para la creación de mapas, también necesitabamos de un diseño de mayor calidad que enrriqueciera la "narrativa cartográfica". Precisamente cuando ya no fue suficiente el solamente compartir datos espaciales en Internet, es que nacen servicios como MapBox, [CartoDB](https://cartodb.com/) o [MapZen](https://mapzen.com/), que buscan además entregar mejores herramientas para la visualización del contenido geográfico.

Para efectos de este tutorial hemos utilizado MapBox para la creación de un Mapa Base. Utilizaremos dicha plataforma por la comodidad que representa a la hora de poder utilizar nuestros diseños en otras plataformas online y offline, como el ya mencionado CartoDB o QGis. Algunos ejemplos de la potencialidad que nos brinda MapBox para la creación de mapas base, lo podemos ver en el servicio que ha creado [Roveda Piergiorgio](http://www.cityplanner.it/), donde provee diseños creados en MapBox principalmente para su uso en la Web. Puedes visitarlo [aquí](http://www.cityplanner.it/map/webgis/leaflet-provider-demo-leaflet-extras/).

El foco de éste tutorial será guiarte en cómo utilizar el mapa base que diseñes en MapBox para cartografías offline, es decir, para mapas impresos o imagenes estáticas utilizando el software de análisis espacial QGis.

> NOTA: para este tutorial necesitas algunos conocimientos básicos de QGis (instalar un plugin - [aquí un buen tutorial](http://www.cursosgis.com/index.php/blog-cursosgis/130-como-anadir-plugins-en-qgis.html) para saber cómo hacerlo en el caso que no sepas) y CSS (básicamente saber qué son los colores expresados en [Hexadecimal](https://en.wikipedia.org/wiki/Web_colors#Shorthand_hexadecimal_form), como por ejemplo "Blanco: #fffff".

### 1.- Preparando las herramientas
Para crear este mapa base personalizado necesitamos de algunas herramientas gratuitas como lo son [MapBox Studio](https://www.mapbox.com) y [QGis](http://www.qgis.org/en/site/). De no utilizar ya estos servicios, puedes de manera sencilla y gratuita crear una cuenta en MapBox. Así mismo puedes descargar, también de forma gratuita el software de análisis espacial QGis desde [aquí](http://www.qgis.org/en/site/forusers/download.html). 

Además para la personalización del mapa base utilizaremos lo siguiente:
- **IOS7 Pallete:** paleta de colores en códigos hexadecimal usados en [IOS7](https://en.wikipedia.org/wiki/IOS_7) (sistema operativo Apple).
- **QuickMapService QGis Plugin:** extensión o plugin de QGis que entrega una lista de mapas base en QGis. El plugin puede ser descargado desde [aquí](https://plugins.qgis.org/plugins/quick_map_services/) o instalado a través de QGis ([ver más](http://www.cursosgis.com/index.php/blog-cursosgis/130-como-anadir-plugins-en-qgis.html)).
- **Procesador de Texto (yo usé Notepad++):** cualquier procesador de texto es suficiente para este ejercicio, como Notepad si usas Windows. Prefiero utilizar Notepad++ ya que es el software que utilizo para crear código regularmente. Lo puedes descargar gratos [aquí](https://notepad-plus-plus.org/download/v6.9.2.html).

Pues bien, ahora comencémos!

### 2.- Diseño en MapBox
Una vez que hayas ingresado a MapBox con tu cuenta, debes ir a la opción "Styles" (Sí, mi cuenta está en inglés). Verás una ventana como esta:

![Styles](https://c1.staticflickr.com/8/7563/27625339712_27e10e117e_b.jpg)

Haz click en "New Style" o "Nuevo Estilo" en la siguiente pantalla:
![New Style](https://c5.staticflickr.com/8/7273/27692111676_0a656d3a2d_b.jpg)

Como ves se despliegan ocho estilos predeterminados y uno "vacío" o empty. Para este ejercicio yo escogí el tema predeterminado "Dark". 

Cuando se abre el editor de MapBox verás un mapa de todo el mundo. Puedes acercar el mapa con el mouse al área que quieras visualizar mientras editas, o buscar un lugar específico con el menu del costado superior derecho, presionando en la lupa. He escogido Madrid como el centro del mapa en esta ocasión, sin embargo debes tener presenta que el mapa base desplegará tu diseño para cualquier área del planeta, es decir, que los colores que escojas por ejemplo para los ríos, será el mismo color en Madrid como en cualquier ciudad del mundo:

![Map_01](https://c1.staticflickr.com/8/7313/27625339272_511c749a3b_b.jpg)

Comenzar a editar el mapa tiene una curva de aprendizaje en mi opinión corta, o sea te toma poco tiempo reconocer que funciona como cualquier otro editor de imagenes, como por ejemplo Photoshop. Lo que me ha resultado más sencillo es escoger con el mouse el atributo que quiero modificar, por ejemplo presiono sobre una ruta para que se desplieguen las características de ese atributo, para luego proceder a editarlo. Tal como se muestra en la siguiente imagen:

![Map_Edit](https://c2.staticflickr.com/8/7413/27725987545_fe5015b7e3_b.jpg)

Para manterner la sencillez de éste tutorial he modificado en este caso solamente los colores del mapa base. Sin embargo puedes modificar el mapa agregando texturas en formato *.svg*, los márgenes, sombras, íconos y fuentes de los textos:

![Edit](https://c6.staticflickr.com/8/7509/27115465253_54a2075ec9_b.jpg)

Para modificar los colores utilizando la paleta IOS7, solo debes copiar el código del color y copiarlo en el atributo en el campo "color". Los cambios se efectuarán de forma automática en el mapa sin necesidad de guardar a cada momento:

![](https://c5.staticflickr.com/8/7600/27113813004_89e54ea555_b.jpg)
![](https://c8.staticflickr.com/8/7457/27651759191_d935b860a9_b.jpg)

Una vez que estas a gusto con los cambios que has realizado, debes presionar en la esquina superior izquierda en la pestaña "Publish" o "Publicar". Antes de aquello puedes cambiar el nombre de tu estilo por el que tu prefieras, en este caso yo escogí el nombre "Madrid_IOS7". Se desplegará una ventana que te mostrará el tema original y los cambios que has realizado en él. Si está todo OK, presiona publicar en esta nueva ventana (Si publicas como un nuevo tema o simplemente lo publicas, no se pierde el mapa base original, que en este caso era "Dark"):

![Publish](https://c7.staticflickr.com/8/7354/27625388822_808c77927c_z.jpg)

Felicidades! Has creado un nuevo mapa base. Ahora puedes compartirlo, usarlo en una aplicación web o móvil, o utilizarlo como un mapa base en QGis, que es lo que haremos ahora. Para esto la ruta que te entrega MapBox, en la opción de la derecha bajo la pestaña "CartoDB". Copia y guarda dicha ruta, que es la que utilizaremos para agregar este mapa base a QGis:

![Ruta](https://c2.staticflickr.com/8/7304/27115464993_c1eefcd6ce_z.jpg)

Puedes ver el mapa base que he creado para este ejercicio en el siguiente **[link](https://api.mapbox.com/styles/v1/crishmill/cipjffbcx004ddfnrlaozdwe9.html?title=true&access_token=pk.eyJ1IjoiY3Jpc2htaWxsIiwiYSI6ImNyb3hfM0kifQ.U0xLPCZv4uMPvo7JZi4uEQ#12.89/40.4094/-3.6969)**.

### 3.- Agregar nuestro estilo a Quick Map Service
Para agregar nuestro estilo al plugin *QuickMapService* en QGis, debes primero (antes de abrir el programa QGis) a la carpeta en donde descargaste QGis en tu ordenador. En mi caso dicha ruta es *"Users>CrisHMill>QGis2>QuickMapService"*. En dicha carpeta encontrarás dos subcarpetas que contienen los mapa base alojados en QuickMapService. Nos centraremos en la carpeta *"User"* que es el lugar en donde alojaremos nuestro estilo. 

Para efecto de resumir este tutorial puedes aprender en detalle como realizar este paso en el [muy buen video tutorial preparado por "QGis Tips"](https://www.youtube.com/watch?v=VChSVZbZSR0). Por otro lado puedes descargar los archivos necesarios que ya he preparado aquí, y solo pegarlos en las carpetas correspondientes como te explicaré a continuación:
- Descarga las carpetas con el estilo Madrid_IOS7 [aquí](https://github.com/crishernandezmaps/TutorialMapaBase)
- Abre en el procesador de texto que prefieras los archivos *Metadata* y *Madrid_IOS7*. Deberías ver lo siguiente:
![](https://c4.staticflickr.com/8/7733/27652131571_09ae6735ee_z.jpg)
![](https://c8.staticflickr.com/8/7471/27652131791_3f22fbf269_z.jpg)
- Debes editar el archivo *Metadata.ini*, y copiar la ruta que guardamos en el paso anterior. En específico la ruta CartoDB. QGis buscará en dicho link el estilo para pedirle a MapBox desplegarlo.

> NOTA: puedes dejar la url tal como está y ocupar el estilo que yo he creado por esta vez, si es que solamente deseas probar esta funcionalidad. ;)

- El paso final es insertar o pegar las carpetas *"Madrid_IOS7"* en las carpetas correspondientes en QuickMapService, a saber: "Data Source" y "Group". Al descargar los archivos ([link a la descarga](https://github.com/crishernandezmaps/TutorialMapaBase)), habrán notado que hay una imagen para cada uno de ellos. En este caso el logo de "No Solo SIG". Dicha imagen será que el ícono que luego veremos en QGis par activar nuestro mapa base. El orden para agregar nuestros archivos a QuickMapService es el siguiente: (i) La carpeta "Madrid_IOS7" que contiene los archivos "Madrid_IOS7.ini y LogoNoSoloSIG.png" pegar en la carpeta que se encuentra en la ruta QuickMapServive/User/Group; (ii) La carpeta "Madrid_IOS7" que contiene los archivos "Metadata.ini y LogoNoSoloSIG.png" pegar en QuickMapService/USer/Data Source. El resultado debiese ser el siguiente:

![groups](https://c2.staticflickr.com/8/7559/27653026811_6b192dec0d_o.png)
![data source](https://c2.staticflickr.com/8/7274/27653026691_085468a674_o.png)

### 4.- Comenzar a utilizar nuestro Mapa Base
Ahora que nuestros archivos ya estan editados y en la ubicación correcta dentro de nuestra carpeta del plugin QuickMapService en QGis, podemos abrir el programa para comenzar a utilizar nuestro mapa base personalizado.

Cuando QGis esté completamente abierto, abre un nuevo proyecto y haz click en la opción QuickMapService:

![](https://c4.staticflickr.com/8/7194/27115464883_562ec47357.jpg)

*Voilá!* Podemos ahora comenzar a utilizar nuestro mapa base. Podemos reconocerlo en la lista que nos provee QuickMapServer en QGis con el nombre que le hemos dado a nuestra creación, que en este caso es Madrid_IOS7. Además por el ícono que le hemos asignado, que es el logo de nuestro blog No Solo SIG.

El resultado final es el siguiente:
![](https://c1.staticflickr.com/8/7662/27694000856_c0dc6e2814_z.jpg)
© [Mapbox](https://www.mapbox.com/about/maps/) © [OpenStreetMap](http://www.openstreetmap.org/copyright)

### Otras consideraciones
- El mapa base que hemos creado modifica los atributos para todo el planeta. Es decir que estos estilos los puedes usar en tus cartografías alrededor del mundo.
- Recuerda siempre en tus versiones en línea y en impresiones o imagenes estáticas copiar la licencia de atribución, que corresponde a MapBox y OpenStreetMap. De esta forma mantenemos estos dos muy buenos servicios open source con nosotros por más tiempo. Puedes saber más sobre la atribución [aquí](https://www.mapbox.com/help/attribution/).
- Recomiendo para el caso de utilizar mapas base en QGis como una imagen estática, remover los "labels" o nombre de los lugares como los nombre de barrios y ciudad, ya que dichas etiquetas están diseñadas para responder a distintos niveles de zoom en el explorador, y no en QGis, por lo que pierden su estilo. Si tu intención es usar tu mapa base en línea, potencia tu creatividad con el uso de fuentes, colores y contornos.

Saludos! ;)


