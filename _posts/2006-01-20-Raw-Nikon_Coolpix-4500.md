---
layout: post
title: Cómo activar el formato RAW y reparar los píxeles muertos en la Nikon Coolpix 4500
---

Uno de los fallos más grandes del sistema de calidad de Nikon, la fabricación y venta de miles de máquinas de fotografiar de la gama compacta Coolpix (como el caso de mi Nikon Coolpix 4500) cuyos sensores CCD presentaban píxeles erróneos ( [Busca Hot Pixel en Google](http://www.google.es/search?num=100&hl=es&q=dead+or+hot+pixel+coolpix&btnG=B%C3%BAsqueda&meta=)) desde el primer día de compra. Los que se dieron cuenta durante el período de garantía de su cámara encontraron respuesta del servicio de garantía, pero para los despistados, como yo, o para las cámara de estos modelos que les ha salido este defecto, todavía se puede hacer algo para arreglar.

Y por otro lado, intento explicar cómo activar el modo de grabación de archivos RAW en estas cámaras, para poder disfrutar más a fondo las características de tu máquina.

![_config.yml]({{ site.baseurl }}/images/2006/P8252524_nikon_cp4500.jpg)

### COMO REPARAR LOS PÍXELES MUERTOS O BLANCOS EN EL CCD

Lo primero deciros que no me considero partidario de ninguna marca en concreto, de hecho desde que me gusta la fotografía han pasado por mis manos cámaras de marcas distintas, creo sólo repetí marca cuando heredé dos cuerpos de Asahi Pentax que mi padre me dio cuando yo era un crio. Con esto quiero eliminar la posibilidad de sesgo en mi opinión acerca de la Nikon Coolpix 4500.

Como bien he dicho es mi primera Nikon y además no es mi cámara compacta principal. La que más utilizo es una Olympus C-5060WZ que va de maravilla. Esta Nikon la compré concretamente el 22 de octubre de 2005, es una pieza que estaba en la exposición de unos grandes almacenes y que la habían estado maltratando desde ni sé cuando. La estuve viendo y estaba sucia, algo rallada externamente y le faltaba la goma de la empuñadura, consulté el precio y me pareció interesante. Me lo pensé y creí que todo lo que tenía lo podría subsanar en casa. Y así fue, la dejé hecha un bombón, limpia, con una nueva goma en la empuñadura, que estoy pensando en volver a cambiar por un retal de piel.

En fin, el funcionamiento todo parecía correcto:

*   Las exposiciones muy buenas.
*   La autonomía algo justita, hay que comprarse una batería de repuesto o te puede dejar tirado.
*   La rapidez no es su fuerte pero es normal en un equipo de este tiempo.
*   Tiene bastantes funciones, todas las deseables.
*   Hay infinidad de accesorios para esta cámara y un montón de páginas de brico tuning donde hacen con esta cámara de todo digiscoping, astrofotografía, macrofotografía, etc.
*   El macro de esta cámara es una pasada.
*   El flash interno es de chichinabo como en todas las cámaras. Para obtener buenos resultados hay que comprar uno externo y lo que no me gusta es la conexión de flash. Debería ser una zapata como toda la vida.

Podéis encontrar una descripción técnica muy completa en: [www.quesabesde.com (en castellano)](http://www.quesabesde.com/camdig/productos/cam199r.asp) [www.dpreview.com (in english)](http://www.dpreview.com/reviews/nikoncp4500/)

A las dos semanas de estar funcionando con ella me di cuenta de que siempre aparecía un pixel blanco en las proximidades de la esquina superior izquierda. Señoras y señores esto merece un enérgico tirón de orejas a los responsables de la principal marca mundial de fabricación de cámaras. Que le pase a uno vale, pero que este problema sea tan comun como para aparecer más de 62.000 coincidencias que hablan del tema cuando haces la búsqueda en [Google](http://www.google.es/search?num=100&hl=es&q=dead+or+hot+pixel+coolpix&btnG=B%C3%BAsqueda&meta=) es demasiado.

Estuve a punto de devolver la cámara con menos de una semana a la tienda, pero un buen amigo en otro foro me comento un enlace a una dirección rusa: [http://e2500.narod.ru/ccd_defect_e.htm](http://e2500.narod.ru/ccd_defect_e.htm)

En esta dirección te puedes descargar un programita que soluciona el problema del pixel blanco, yo lo acabo de hacer y me funcionado, he utilizado la versión 0.14 del programa. Lo descomprimes en una carpeta, vuelves a descomprimir un archivo zip que lleva dentro de la misma carpeta, conectas la cámara al ordenador a traves del usb en modo usb.storage, ejecutas el programita y detecta tu cámara, le das al botón de REMAP y aceptas el riesgo que esto supone. A mi me ha funcionado, tenía 236 pixeles defectuosos y los a corregido.

### CÓMO ACTIVAR LA ESCRITURA DE ARCHIVOS RAW

Estas cámaras no guardan archivos RAW con los ajustes que traen de fábrica, pero en el funcionamiento interior de todas las cámaras siempre se funciona con información bruta del CCD, se guarde o no esta información. Bueno, pues después de una búsqueda por la red y de haber leido unos cuantos comentarios me decidí a "hackear", mi Coolpix 4500, para poder obtener archivos RAW.

Básicamente se trata de cambiar un ajuste interno de la cámara (no accesible desde los menús) para que ésta funcione en un modo de diagnóstico conocido como "DIAG RAW" (este modo se usa en los servicios técnicos) de manera que cuando haces una foto, la cámara guarda dos archivos jpg o tif dependiendo la calidad de fotografía que tengas seleccionada, con números correlativos, por ejemplo: DSCN1199.JPG (2,2 MB) y DSCN1200.JPG (5,6 MB), ambos archivos son necesarios para decodificar la información raw. El primer archivo es la foto como se habría guardado habitualmente, pero el segundo archivo, aunque termine en jpg se trata de la información raw del CCD y por tanto, cuando pones la cámara en modo de reproducción podrás ver: un archivo sí, y otro no (porque no disponemos en nuestra cámara de un intérprete de la información raw).

Pero que hacemos con estos archivos, con qué los podemos decodificar. Si nuestro sistema operativo es GNU/Linux, no hay problema porque este tipo de archivos está soportado por el software dcraw y por tanto se lee directamente con cualquiera de las utilidades de tratamiento de archivos raw, como por ejemplo ufraw. Si tu sistema operativo es otro puedes utilizar un conversor de archivos que te convertirá estos archivos a los típicos de Nikon [RAW to NEF](http://e2500.narod.ru/raw2nef_e.htm), ó [RAW to DNG](http://e2500.narod.ru/raw2dng_e.htm). Pero recuerda que para poder decodificar estos archivos, debes de tener en la misma carpeta los DOS jpg correlativos, el archivo grande tiene la información raw, pero el archivo pequeño tiene la información de la fotografía, ambos archivos se utilizarán por dcraw o por los programas conversores "RAW to NEF" o "RAW to DNG".

### PROCEDIMIENTO DE CAMBIO DE CONFIGURACIÓN DE LA CÁMARA

Este proceso puede parecer muy delicado, pero llevando un mínimo de precauciones no debe de dar problemas. Sería conveniente que si canectas la cámara al ordenador las pilas estén perfectamente cargadas, quedarse sin pilas a mitad de proceso, no sé que produciría, pero nada bueno seguro; asegurate de que la cámara está bien conectada y que se encuentra en un lugar seguro de enganchones o tropiezos.

Para comunicarme con la cámara yo he utilizado la utilidad photopc en GNU/Linux, pero también a otras utilidades para otros sistemas operativos que comentaré después.

Debemos de tener instalado photopc y en perfecta comunicación con nuestra cámara, si necesitas ayuda puedes encontrarla [AQUÍ](http://www.linux-magazine.com/issue/24/photopc.pdf#search=%22%2Fdev%2Fphotopc%22). Una vez que lo tenemos funcionando hacemos lo siguiente:

**PARA ACTIVAR RAW:**

```

$ photopc id "DIAG RAW"

```

**PARA DESACTIVAR RAW:**

```

$ photopc id "NIKON DIGITAL CAMERA"

```

Así de sencillo, si por el contrario tu sistema operativo es windows puedes usar el programa [Coolpix RAW Enabler](http://e2500.narod.ru/raw_format_e.htm#cpixraw), que sólo tienes que descargar el archivo, descomprimirlo y ejecutarlo, sale una ventanita con una pestaña, si está activada la pestaña está activo el RAW, y si no pues no.
