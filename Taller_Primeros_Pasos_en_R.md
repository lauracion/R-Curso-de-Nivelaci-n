# Curso: Primeros pasos en R

### Modificado por Laura Ación (original de [Riva Quiroga](https://twitter.com/rivaquiroga))

## ¿Qué es R?

R es un lenguaje de programación de código abierto (es decir, gratuito y en el que se puede saber exactamente cómo funciona). Por razones históricas, R tiene un fuerte énfasis en el análisis estadístico de datos. Su desarrollo inicial estuvo a cargo de Robert Gentleman y Ross Ihaka del Departamento de Estadística de la Universidad de Auckland en 1993. Desde entonces creció mucho y se ha vuelto un lenguaje muy popular entre quienes analizan datos.

Por su versatilidad, R es muy usado en todas las disciplinas que incluyen datos y, por supuesto, en Ciencia de Datos. Con R se puede programar todo tipo de análisis ya que cuenta con herramientas de matemática y estadística, machine learning, procesamiento de señales (por ejemplo, sonido e imágenes), todo tipo de simulaciones, modelado y testeo estadístico. También se puede analizar Big Data usando R. Con R se obtiene fácilmente visualizaciones de datos de muy buena calidad que pueden ser estáticas, dinámicas o interactivas. R también permite la generación automática de reportes que informan los resultados de análisis de datos a quienes no les interesan los detalles finos de cómo se realizó un análisis. Como con cualquier otro lenguaje de programación, el límite de lo que se puede hacer con R es sólo la imaginación de sus usuarios. 

R es un gran aliado para realizar Ciencia de Datos reproducible tanto por tu yo futuro como por otros con quienes compartas tu trabajo.

## Objetivo del curso

El objetivo de este curso es acompañar a principiantes en el proceso que va desde la instalación de R a la manipulación inicial de datos. 

La idea es que sea algo práctico y a la vez suficientemente explicativo como para que se entienda qué es lo que hace cada bloque de código.

El curso contiene imágenes, con el fin de ir ilustrando el proceso tal como debería verse en tu computadora.

_________

### IMPORTANTE
Es esencial que todo lo que sigue a estas líneas se haga antes de concurrir en forma presencial al Curso de Nivelación. Caso contrario, es posible que no puedas practicar en tu computadora los pasos que siguirán durante el curso.

_________

## Instalación de R y RStudio

En este curso utilizaremos R a través del IDE RStudio. 

¿Qué es un IDE? IDE es el acrónimo de *Integrated Development Environment* (*Entorno de Desarrollo Integrado*). Esto quiere decir que RStudio es una aplicación que nos entrega herramientas para hacer más fácil el desarrollo de proyectos usando R.

Para poder instalar R y RStudio, seguí los siguientes pasos:

- Descargá R desde https://cran.r-project.org/. Debés elegir la opción que corresponda, según tu sistema operativo.
- Instalá R en tu computadora, tal como lo hacés con cualquier programa. 
- Una vez que R quedó correctamente instalado, descargá RStudio desde https://www.rstudio.com/products/rstudio/download/. Elegí la primera opción, es decir, "RStudio Desktop Open Source License" (gratuita). 
- Instalá RStudio en tu computadora, tal como lo hacés con cualquier programa. 

Para un paso a paso que incluye imágenes de este proceso de instalación podés ir a [este archivo](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/Instalacion_R_RStudio.pdf). 
Si quedó todo bien instalado, cuando abras RStudio deberías ver algo así:

![](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio.png)

En este curso usaremos la última versión de R y RStudio, así que si tenés instalada una versión previa, puede que algunas cosas se vean un poco distintas.

IMPORTANTE: Si aparece algún error durante este proceso, lo más probabable es que sea por alguna configuración de tu sistema operativo. En ese caso, la mejor manera de buscar una solución es copiar el error que arroja R, pegarlo en, por ejemplo, Google y ver cómo alguien que se enfrentó a eso antes lo resolvió. Si no lográs solucionarlo, veremos problemas que hayan surgido personalmente durante el transcurso del curso.

## Instalación de los paquetes de R que utilizaremos

Cuando instalamos R por primera vez en la computadora, lo que estamos instalando es lo que se conoce como "R Base", es decir, los elementos centrales del lenguaje de programación. Una de las ventajas de R es que se trata de un lenguaje extensible: la propia comunidad de usuarios puede desarrollar nuevas posibilidades para utilizarlo. La manera de compartir estos nuevos desarrollos es a través de "paquetes", que incluyen, entre otras cosas, código y datos. Una analogía que se suele utilizar para explicar esto es que R Base es un teléfono celular tal como viene de fábrica y los paquetes las _apps_ que descargamos para que tenga más funcionalidades. 

En este curso usaremos tres paquetes: `gapminder`, `babynames` y `tidyverse`. Los dos primeros (`gapminder` y `babynames`) son paquetes que incluyen datos que nos servirán para algunos de los ejercicios que realizaremos. `tidyverse`, por su parte, es un "megapaquete" que incluye otros paquetes en su interior. Todos los paquetes que conforman "el Tidyverse" comparten la misma visión sobre el trabajo con datos y la escritura de código. Quizás ahora eso suene un poco enigmático, pero más adelante explicaremos qué quiere decir. 

Para instalarlos, 

1. copiá el siguiente código:

```r
install.packages("tidyverse")
install.packages("gapminder")
install.packages("babynames")
```

2. pegálo en la consola (_Console_) de RStudio:

![](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/install.packages.png)

3. presioná 'enter'. 
Dependiendo de tu conexión a internet instalar todos los paquetes podría tomar unos minutos. El resultado se debería ver parecido a esto:

![](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/paquetes_instalados.png)

¿Salió todo bien? ¡Excelente! Felicitaciones. Ya escribiste tus primeras tres líneas de código en R.

#### Warnings / Errores
Si no tenés la última versión de R, puede que aparezca un "Warning" durante la instalación, que te avisa que el paquete fue construido bajo otra versión de R. Un "Warning" es distinto a un error: R ejecuta el código que le pidas, pero advierte que no todo puede resultar como esperas. Cuando aparece un error, en cambio, el código no se ejecuta. 

_________


## Utilización de RStudio

Como señalamos antes, RStudio es un entorno que facilita el trabajo con R. Si sólo abrís R en tu computadora, lo que verás es una consola. Cuando trabajamos en ella escribimos directamente el código que queremos que se ejecute. El signo `>` nos indica que R está listo y esperando que escribamos algo.

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/r_consola.png" align="center" height="400"></a>

Si abrís RStudio verás que te aparece la misma consola, pero además te encontrarás con otros paneles. Estos paneles nos ayudan a organizar nuestro trabajo y hacen todo el proceso más sencillo. 

![](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio.png)

¿Para qué sirven estos paneles? Comentemos primero el panel de abajo a la derecha. Si te fijás, el panel tiene varias ventanas: 

* __Files__ muestra el directorio (la carpeta) en la que te encuentras actualmente. En el caso de la imagen, no hay nada ahí porque por defecto RStudio me muestra el Escritorio (_Desktop_) y no hay nada en él. Es posible que te muestre otra carpeta (por ejemplo, _Documentos_). 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_files.png" align="center" width="50%"></a>

* __Plots__ es el lugar donde aparecerán los gráficos que crees. No hicimos ninguno por ahora, así que este panel también está vacío. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_plots.png" align="center" width="50%"></a>

* __Packages__ muestra la lista de paquetes que tenés instalados en tu computadora. Si recorrés el panel verás que algunos tienen una marca a la izquierda. Eso quiere decir que el paquete está activo en ese momento (ya veremos cómo activar los paquetes que usaremos). Sólo los paquetes vinculados a R base se activan al abrir RStudio. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_packages.png" align="center" width="50%"></a>

* __Help__, como su nombre lo indica, es la pestaña en la que podemos encontrar ayuda. Si buscamos el nombre de un paquete o de una función, RStudio nos remitirá a la documentación asociada. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_help.png" align="center" width="50%"></a>

* __Viewer__ es el panel para ver contenido web generado por algún paquete de R (gráficos para la web o aplicaciones interactivas - sí, leiste bien, con RStudio se pueden hacer aplicaciones interactivas). Por el momento no lo utilizaremos. 

El panel de arriba a la derecha, por su parte, contiene el historial de funciones que ejecutamos (_History_). ¿Qué dice tu _History_? 

La opción para generar conexiones a bases de datos externas (_Connections_) y el _Environment_. Este último panel es muy importante y entender lo que nos muestra es fundamental para comprender cómo funciona R. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_globalenvironment.png" align="center" width="50%"></a>

Por ahora está vacío porque no hemos creado ninguna variable ni ningún otro objeto, pero cuando creemos alguno es aquí donde aparecerá. Volveremos a hablar sobre este panel cuando comencemos a trabajar con datos. 

Hay un cuarto panel (que probablemente todavía no te aparece)  y que es el que utilizamos para escribir el código que queremos que R ejecute, es decir, el panel para nuestro _script_ (o secuencia de comandos). Para crear un nuevo script podemos:
* ir a File > New File > R Script
* usar el atajo de teclado `comando` + `shift` + `n` (Mac) o `control` + `shift` + `n` (Linux / Windows)
* o seleccionar la opción desde la barra superior de la ventana:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/nuevo_script.png" align="center" width="60%"></a>

¡Ahora ya están los cuatro paneles!

### Creación de un proyecto 

Una de las ventajas de RStudio es que permite crear "proyectos". Un proyecto es un espacio o contexto de trabajo asociado a una carpeta en particular, en la que se guardan nuestro(s) script(s), archivos de datos, etc. Cuando creamos un proyecto en RStudio, se crea un tipo especial de archivo que termina en .Rproj. Este archivo vincula todo lo que se encuentra dentro de esa carpeta. 

¿Por qué esto es útil? Si parte de nuestro script, por ejemplo, implica abrir un archivo que está en la carpeta de nuestro proyecto, no necesito indicar en mi código dónde se encuentra ese archivo en mi computadora. Lo que hará RStudio será buscarlo en el entorno/carpeta del proyecto. Si movemos la carpeta a otro lugar de nuestra computadora o la compartimos con otra persona, nuestro código seguirá funcionando, ya que el archivo .Rproj mantendrá todo unido. 

Si no creara un proyecto, tendría que indicar al inicio de mi script cuál es la ruta de la carpeta que usaré como espacio de trabajo. El problema de esa opción es que si muevo la carpeta o le cambio el nombre, tendría que volver a escribir la ruta para que todo funcione. Al crear un proyecto eso deja de ser una preocupación. 

Cuando uno no usa proyectos, es común ver que los scripts comienzan con la función `setwd("[ruta al directorio donde se encuentra el script]")`. Por ejemplo `setwd("C:\Laura\Stats")`.  Esta es una costumbre arraigada entre muchos expertos de R que usan R desde antes que existiera la posibilidad de usar poryectos dentro de RStudio (e incluso desde antes de que existiera RStudio). La práctica actual recomendada es trabajar usando proyectos.

¿Cómo crear un proyecto? Podés hacerlo desde el menú File > New Proyect. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_newproject1.png" align="center" width="50%"></a>

Lo primero que nos pregunta es si queremos crearlo en una carpeta nueva o en una ya existente. Elegiremos esta vez una carpeta nueva, así que seleccionaremos _New Directory_. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_newproject2.png" align="center" width="50%"></a>

La siguiente pregunta es qué tipo de proyecto queremos crear. En esta ocasión, elegiremos la primera: _New Project_.

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_newproject3.png" align="center" width="50%"></a>

Finalmente, le damos un nombre al proyecto y decidimos en qué parte de nuestra computadora queremos que viva la carpeta que lo contiene. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_newproject4.png" align="center" width="50%"></a>

Luego de apretar _Create Project_, RStudio se reinicia y se producen algunos cambios. El panel _Files_ (abajo a la derecha) ahora nos muestra la carpeta de nuestro proyecto y el único archivo que hay en ella por ahora. Ese es el archivo "mágico" que mantiene unido todo lo que hay dentro de la carpeta. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_rproj.png" align="center" width="50%"></a>

Otro cambio que ocurre es que en la barra superior aparece ahora la ruta de la carpeta de nuestro proyecto. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio_barraproyecto.png" align="center" width="100%"></a>

Cuando cerremos RStudio y queramos volver a trabajar en este proyecto, bastará con ir al directorio que creamos para el proyecto y abrir el archivo .Rproj. 

Esto último es _enormemente_ útil. RStudio ejecuta sesiones independientes de R para cada proyecto. Es decir, si tuvieras otro proyecto abierto te aparecería otro ícono, con su respectivo nombre. Esto nos permite trabajar en dos proyectos en paralelo sin que se nos mezclen los objetos y variables del entorno, el código, los archivos, etc. Cada cosa en su lugar facilita que cometamos muchos menos errores.

Ya tenemos todo listo para empezar a trabajar con datos.

## Cargar los paquetes necesarios

Si completaste los pasos de preparación que se habían recomendado antes de venir hoy, ya tenés instalados los paquetes que usarás en el curso. Cada vez que instalamos un paquete queda en nuestra computadora. Podemos chequear eso revisando el panel "Packages" abajo a la derecha. Sin embargo, que los hayamos instalado no quiere decir que estén listos para ser usados. Tenemos que decirle explícitamente a R qué paquetes queremos usar en cada sesión (no tiene sentido tener activos paquetes que no estamos utilizando).

La función para llamar o activar un paquete es `library(nombre_del_paquete)`, así que escribiremos eso al inicio de nuestro script. Si no tenés un script abierto, simplemente seguí los pasos comentados más arriba (File > New File > R Script).

RStudio trata de hacernos la vida más simple, así que cuando empezamos a escribir se despliega un menú con posibles opciones que indican el nombre de la función y el paquete al que está asociada (en este caso, es una función de R `{base}`). Lo que aparece en amarillo es la estructura de la función, algo sobre lo que hablaremos más adelante.

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/sugerencia_funcion.png" align="center" width="50%"></a>

Lo mismo ocurre cuando empezamos a escribir el nombre del paquete. RStudio nos va ofreciendo sugerencias a partir de los paquetes que tenemos instalados: 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/sugerencia_argumento.png" align="center" width="50%"></a>


Todavía no hemos "ejecutado" el código, así que no pasó nada. Como todo en R, hay varias opciones para hacer esto. Si hacemos clic en el botón _Run_ que está en la barra del script, se ejecutará la línea de código en la que está actualmente el cursor y éste se moverá automáticamente a la siguiente línea. Es decir, si ponemos el cursor en la línea en la que llamamos por primera vez la función `library` y hacemos clic tres veces, se ejecutarán las tres líneas. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/ejecutar_codigo.png" align="center" width="50%"></a>

Eso mismo podemos hacerlo usando el atajo de teclado `ctrl` + `enter` (si estás en Linux o Windows) o `comando` + `enter` si estás en Mac. 

Cuando queremos ejecutar más de una línea de código, lo que podemos hacer es seleccionar todo el fragmento y hacer clic sobre Run o usar el atajo del teclado. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/seleccion_para_ejecutar_png.png" align="center" width="50%"></a>


¡Ejecutemos el código y veamos qué pasa!


<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/codigo_ejecutado.png" align="center" width="50%"></a>

Cuando ejecutamos el código de nuestro script, éste pasa a la consola. En el caso del primer paquete (`tidyverse`), la consola nos da dos avisos. El primero, cuáles son todos los paquetes que estamos cargando al cargar el `tidyverse`. Como comentamos antes, este es un megapaquete que incluye otros paquetes en su interior. Al llamarlos a través de `library(tidyverse)` se activan 8 paquetes (pese a que el Tidyverse incluye más). Eso es lo que nos está avisando R en la consola. El otro aviso es de un "Conflicto". Nos dice que las funciones `filter()`y `lag()` del paquete `dplyr` tienen el mismo nombre que funciones del paquete `stats` (que es parte de R base). Como cargamos `dplyr`después (al instalar `tidyverse`), lo que R nos avisa es que son las funciones de este último paquete las que van a prevalecer por sobre las del paquete `stats`.

__IMPORTANTE__: Lo que hicimos recién fue cargar los paquetes __para esta sesión__ de R que estamos ejecutando actualmente. Si en algún momento cerraras el programa y retomaras este tutorial en otro momento, tendrías que volver a ejecutar estas líneas. 

### Buenas prácticas

En este punto es importante sugerir dos buenas prácticas. 

La primera, es hacer lo que ya hicimos: llamar todos los paquetes que usaremos al inicio de nuestro script. De este modo, cuando volvemos a trabajar con él más adelante (u otra persona quiera ejecutarlo) queda claro desde el principio qué paquetes se utilizan (y sería necesario descargar usando `install.packages`, en caso de no tenerlos). 

Obviamente, cuando comenzamos a escribir un script no siempre sabemos cuáles son todos los paquetes que necesitaremos. Por eso, si en la mitad del proceso decido usar un nuevo paquete, la buena práctica sería volver a las primeras líneas del script y agregarlo. 

La segunda buena práctica es comentar nuestro script. En R podemos agregar comentarios anteponiendo un `#` a la línea que contenga un comentario. En una línea de nuestro script, todo lo que está después de un `#` no se ejecuta como código a apretar el botón _Run_. 

¿Por qué es importante comentar nuestro script? Porque así podemos recordar qué es lo que un determinado fragmento de código hace, o podemos dejar registro de por qué realizamos algo de una determinada manera. Esto es muy útil para que nuestro futuro yo (o las personas con las que compartiremos nuestro script) entiendan lo que hicimos. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/comentarios.png" align="center" width="35%"></a>

¡Los comentarios también son muy útiles cuando estamos aprendiendo! Probablemente en el futuro ya no necesites indicar que `library()` sirve para cargar paquetes, pero por ahora es una buena manera de ir registrando qué es lo que hace cada función.

También es útil agregar al inicio de nuestro script una descripción de su objetivo o del contexto en que lo escribimos: 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/comentario_inicio_script.png" align="center" width="60%"></a>

Si te fijás, nuestro script aún dice Untitled1. Antes de seguir, es importante que lo guardemos. Y lo podés hacer como en cualquier otro programa: con `Control/Comando` + `S`. RStudio te ofrecerá por defecto guardarlo en la carpeta de tu proyecto. Cuando ya esté guardado, te aparecerá en la pestaña _Files_.  

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/guardar_script.png" align="center" width="75%"></a>

Es recomendable aprender a usar atajos del teclado como `Control + S` porque son más rápidos que usar el mouse y apretar botones. Ahorran mucho tiempo en el largo plazo.


## Una mirada inicial a los datos

`babynames` es un paquete que contiene datos sobre nombres registrados en Estados Unidos entre los años 1880 y 2015. El "objeto" que contiene los datos dentro del paquete se llama también `babynames`. En R, podemos ver un objeto simplemente ejecutándolo. Es decir, escribimos el nombre del objeto y ejecutamos el código. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/ejecutar_babynames.png" width="60%"></a>

De ahora en adelante, en vez de mostrarte una imagen del script, el código que haya que ir ejecutando en el curso aparecerá en un recuadro, así:

```r
babynames
```
En la consola, veremos las primeras líneas de este objeto que contiene datos:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/objeto_babynames.png" width="70%"></a>

¿Dónde está este objeto? No lo vemos en nuestro Global Environment porque no lo hemos creado nosotros. Sin embargo, a través de ese panel podemos acceder al "environment" de todos los paquetes activos. En el de `babynames` lo encontraremos: 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/entorno_babynames.png" width="40%"></a>

En este caso, el objeto `babynames` es una `tibble`, que es un tipo particular de conjunto de datos. No nos detendremos aún en los tipos de objetos que existen en R; lo importante por ahora es saber que R nos muestra en la consola las primeras diez filas de una "tibble" para que nos hagamos una idea de lo que contiene (y no las casi dos millones de filas que tiene este objeto en particular). 

Si quisiéramos tener una visión general de los datos, hay una función que resulta muy útil para esto, ya que nos los muestra en una pestaña distinta: `View()`. 

``` r
View(babynames)
```
Si ejecutás ese código, una nueva pestaña se abrirá y te mostrará todos los datos en un formato tipo planilla (casi como un Excell), que podés recorrer, filtrar y ordenar, pero no editar. Esto es muy importante para mantener la buena calidad de los datos.

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/babynames.png" width="100%"></a>


Existen otras funciones útiles para darle una primera mirada a nuestros datos: `head()` y `tail()`. Como su nombre lo indica, lo que hacen es mostrarnos las primeras y las últimas líneas de nuestros datos, respectivamente. 

``` r
head(babynames)
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/head_babynames.png" width="75%"></a>

``` r
tail(babynames)
```

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/tail_babynames.png" width="75%"></a>


Las funciones `tail` y `head` resultan muy útiles para chequear si nuestros datos están completos, ya que nos permiten mirar sus extremos.

Si queremos conocer la estructura de nuestro conjunto de datos, es decir, conocer la cantidad de observaciones, de variables y de qué tipo son, podemos utilizar  `str()`.

```r
str(babynames)
```

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/str_babynames.png" width="75%"></a>


### Algo más sobre las funciones

Hasta el momento usamos funciones en las que indicamos un solo "argumento" dentro del paréntesis: el nombre del objeto que queremos ver. Sin embargo, todas estas funciones tienen más argumentos. Lo que ocurre es que hemos utilizado los valores que vienen por defecto (por ejemplo, salvo que indiquemos algo distinto, `head()` y `tail()` solo nos mostrarán 6 filas). 

Si queremos conocer cuáles son los otros argumentos que acepta una determinada función, podemos buscarla en el panel _Help_ o directamente tecleando en la consola: `?función`, por ejemplo:

```r
?tail
```
Si leemos la ayuda podemos enterarnos que `tail` permite definir la cantidad de filas que se muestran como segundo argumento de la función. Si en vez de las 6 líneas por defecto quiero que me aparezcan 10, tendría que indicarlo así:

```r
tail(babynames, n = 10)
```

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/tail_babynames_n10.png" align="center" width="75%"></a>


Es importante tener en cuenta que las funciones leen sus argumentos en orden, por lo que si en la ayuda vemos que el segundo argumento de `tail` es `n =`, podríamos solo escribir el número de líneas que queremos, es decir, así:

```r
tail(babynames, 10)
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/tail_babynames_10.png" align="center" width="75%"></a>


¡El resultado es el mismo! 
Puedo poner los argumentos en otro orden sólo si indico explícitamente a qué argumento corresponde cada uno. Es decir, esto funciona:

```r
tail(n = 10, x = babynames)
```

¿Y esto, funcionará? Probá ejecutando el código para que ver lo que ocurre:
```r
tail(10, babynames)
```

### Intepretar errores

Un error que es muy habitual cometer en R es escribir mal el nombre de un objeto o de una función. Como R distingue entre mayúsculas y minúsculas, `babynames` no es lo mismo que `Babynames`. De hecho, si tratamos de utilizar este último nombre R nos arrojará un error: `Error: object 'Babynames' not found`. 

Cuando te aparezca este tipo de error, revisá si el nombre del objeto o de la función que querés usar está bien escrito. Este error también aparece cuando cargamos el paquete en que se encuentra un determinado objeto o función usando `library(paquete)`. 

Como uno casi nunca es la primera persona que enfrentó un error, la manera más rápida de buscar ayuda es copiar el error, pegarlo en Google y ver cómo alguien ya recibió ayuda para resolverlo.

## Exploración y manipulación de los datos

Ahora que ya dimos una mirada inicial al conjunto de datos con el que estamos trabajando, podemos empezar a explorarlo y responder preguntas. Por ejemplo, mientras esperamos el estreno de la última temporada de Game of Thrones, podríamos querer saber a cuántas personas le han puesto el nombre de una de sus protagonistas: "Daenerys". Para eso podemos utilizar el siguiente código:

```r
babynames %>% 
    filter(name == "Daenerys")
```

¿Qué hace este código? Con él le estamos diciendo a R que :
* tome el objeto `babynames` 
* luego (` %>% `) 
* que filtre (`filter`) los nombres (`name`) que sean iguales `==` a `Daenerys`. 

Por convención, después de ` %>% ` nos saltamos una línea (sin ella el código igual funciona). Se hace así para que sea más fácil de leer (por ahora no se nota mucho la diferencia, porque el bloque de código es pequeño). 

Si lo ejecutamos, podemos ver el siguiente resultado:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/filter_daenerys.png" align="center" width="75%"></a>

¡Las primeras Daenerys aparecen en 2012! 

¿Por qué usamos `==` y no `=`? Usamos `==` porque lo que le estamos pidiendo a R es que busque los casos en los que el valor de la variable `name` sea igual a "Daenerys". En R (y en otros lenguajes de programación) el signo `=` se utiliza para asignar valores (¡lo haremos más adelante!).

Una de las ventajas de algunos paquetes de R (como los del Tidyverse) es que tratan de que los mensajes de error sean informativos. Prueba ejecutar el código anterior cometiendo el error de usar `=` en vez de `==`:

```r
babynames %>% 
    filter(name = "Daenerys")
```
¿Qué dice el mensaje de error?

No solo nos indica cuál es el problema, sino que también nos da una sugerencia para resolverlo.

Podemos seguir usando ese mismo código de filtrado para buscar otros nombres. Sólo tenemos que cambiar el valor que queremos que tenga la variable `name`. Busquemos otros personajes de Game of Thrones:

```r
babynames %>% 
    filter(name == "Sansa")
```

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/sansas.png" align="center" width="50%"></a>

Al parecer Sansa no ha sido un nombre tan popular como Daenerys. Al menos no hasta 2015. ¿Y Arya?

```r
babynames %>% 
    filter(name == "Arya")
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/filter_arya.png" align="center" width="60%"></a>

¡Hay muchas más Aryas! Y aparecen antes (o sea, por influencia del libro y no de la serie, como en los otros dos casos). Hay tantas Aryas que no alcanzan a imprimirse en la consola. ¿Cómo podríamos saber cuántas hay en total? En la siguiente sección lo veremos.

### Cómo resumir datos y un poco más acerca del operador ` %>% `

Antes de responder la pregunta que planteamos en la sección anterior, hablemos un poco del símbolo ` %>% `. ¿Qué es ` %>% `? Este símbolo se llama _pipe_ (_tubo_ en inglés) y en el código lo podemos leer como "luego" o "a continuación". El atajo del teclado para realizarlo es `control` + `shift` + `m` (Linux / Windows) o `comando` + `shift` + `m` (Mac).

`%>%`es un operador que nos permite encadenar las acciones que queremos aplicar en un objeto (en este caso, `babynames`). Por ejemplo, si quisiéramos saber a cuántas personas se llaman Arya, podríamos agregar otra función al código que estábamos usando que sume todos los valores de la columna `n` (la que tiene la cantidad de nombres por año). La función que nos sirve para eso es `summarize` (o `summarise`; R acepta inglés norteamericano o británico). Como su nombre lo indica, lo que hace `summarize` es resumir información, según el criterio que le entreguemos. Veamos cómo funciona:

```r
babynames %>% 
    filter(name == "Arya") %>% 
    summarize(sum(n))
```
Con este código le estamos diciendo a R que :

* tome el objeto `babynames` 
* luego (` %>% `) 
* que filtre los nombres que sean iguales a Arya (`filter(name == "Arya")`)
* luego (` %>% `)
* que resuma (`summarize`) la siguiente información:
* la suma (`sum`) de los valores de la columna `n`. 

¿Qué pasa si ejecutamos este código? ¡8866 Aryas!

Para que quede más claro por qué decimos que `summarize` resume, agreguemos otros criterios: que nos dé el promedio de Aryas por año (`mean`) y en qué año se usó por primera vez (`first`).

```r
babynames %>% 
    filter(name == "Arya") %>% 
    summarize(sum(n), mean(n), first(year))
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/summarize_arya.png" align="center" width="75%"></a>

Lo que hizo `summarize` fue resumir toda la información que le pedimos en una tabla (un nuevo `tibble` u objeto de datos que incluye los tres estadísticos que pedimos). 

Es probable que la cantidad de decimales que te aparece sea distinta. Depende de la configuración de cada equipo.

### Distintos tipos de sintaxis

Más arriba comentamos que el Tidyverse era un conjunto de paquetes que compartía un mismo enfoque de trabajo con los datos. Una de las características de este enfoque se relaciona con la forma de escribir el código, es decir, con su _sintaxis_. 

La sintaxis de los paquetes del Tidyverse utiliza el operador ` %>% ` que vimos más arriba. El pipe permite organizar el código de modo que lo leamos de arriba hacia abajo y de izquierda a derecha (la orientación que suele tener nuestra lectura). 

Hagamos una comparación entre la sintaxis del Tidyverse y la sintaxis de R base. Si quisiéramos contar la cantidad de Aryas usando la sintaxis propia del Tidyverse, lo haríamos así:

```r
babynames %>% 
    filter(name == "Arya") %>% 
    summarize(sum(n))
```

Si hiciéramos lo mismo usando la sintaxis "tradicional" (la de R base) nuestro código se vería así:

```r
sum(babynames$n[babynames$name == "Arya"])
```

Ambos códigos hacen exactamente lo mismo y llegan al mismo resultado: 8866. Probá ejecutándolo. 

La diferencia es que el primero que escribimos (usando ` %>% `) "desempaqueta" las acciones, lo que lo hace más intuitivo de leer. En el caso del segundo, tenemos que leer de adentro hacia afuera para comprender la secuencia de acciones realizadas sobre los datos. Además, para facilitar la comprensión, los paquetes del Tidyverse suelen tener nombres de funciones que resultan transparentes (aunque están en inglés, claro). 

Existe algunos tipos de análisis estadísticos para los que no es posible aplicar la sintaxis del Tidyverse, tipos de datos con los que no es compatible o situaciones en las que, por un tema de procesamiento (muchos datos), resulta mejor usar la sintaxis de R base (u otras como las de `data.table`). La buena noticia es que con el tiempo y uso, uno se va acostumbrando a esa manera de escribir el código. 

De todos modos, para la mayoría de las operaciones de importación, limpieza, exploración y manipulación de datos rectangulares podemos utilizar la sintaxis del Tidyverse sin problema.

Muy pocas personas "hablan" R tan bien como para escribirlo fluídamente. La mayoría de los mortales solemos buscar en Google cómo hacer la mayoría de lo que queremos hacer. Es muy común copiar, pegar y modificar código de otros usuarios. Afortunadamente, la comunidad de usuarios de R es muy prolífica. De hecho, es posible encontrar formas de escribir R en varias sintaxis. Si uno está trabajando usando el Tidyverse, conviene agregar la palabra Tidyverse en la búsqueda para obtener resultados que sigan esa sintaxis.

### Creación de objetos

Hasta el momento hemos realizado una serie de acciones sobre el objeto `babynames`: hemos filtrado información y hemos hecho cálculos en una variable. Sin embargo, el tibble `babynames` no cambió. Si volvés a imprimir en la consola el contenido de ese objeto, tendrás los mismos resultados que al principio.

```r
babynames
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/objeto_babynames.png" width="70%"></a>

Imaginá que nos interesa guardar los datos sobre la cantidad de Aryas porque seguiremos trabajando sólo con ellos y el resto no nos interesa. Para no tener que filtrar cada vez que los queramos usar, conviene crear un nuevo objeto. 

En R eso lo hacemos con el símbolo de asignación: `<-`. ¿Cómo funciona? Lo que está a la izquierda del símbolo de asignación es el objeto que queremos crear y lo que está a su derecha es el valor que queremos asignarle. Así:

```r
aryas <- babynames %>% 
    filter(name == "Arya")
```
Este código crea un nuevo objeto llamado `aryas`, cuyo valor contiene lo que resulta de aplicar un filtro a `babynames`. Si ejecutás ese código, no aparecerá nada nuevo en la consola (salvo el código que acabás de ejecutar). Sin embargo, en nuestro _Global Enviroment_ (el panel de arriba a la derecha) aparecerá el objeto que creamos:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/aryas.png" align="center" width="40%"></a>

Ahora podemos llamar a ese objeto tal como hicimos con `babynames`. 

```r
aryas
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/objeto_aryas.png" align="center" width="70%"></a>

Hacer clic sobre cualquier objeto del _Global Environmet_ es equivalente a aplicar la función `View()`. Hacé la prueba: si hacés clic sobre `aryas`, se abrirá una nueva pestaña en el panel de tu script en el que verás el objeto como una planilla. En la consola, aparecerá automáticamente el código para realizar esa acción `View(aryas)`.

NOTA: el atajo de teclado para escribir `<-` es `alt` + `-`.

## Más funciones para explorar y manipular datos

Trabajemos ahora con el paquete `gapminder`. Este paquete contiene una parte de los datos de Gapminder, una base de datos que incluye información mundial sobre población, expectativa de vida, PBI per cápita y otros. Su autor, Hans Rosling, fue un médico sueco que trabajó en salud global y era una gran orador. [Aquí algunas de sus charlas imperdibles](https://www.ted.com/playlists/474/the_best_hans_rosling_talks_yo).


Podemos dar una mirada inicial a los datos usando las funciones que ya revisamos:

```r
str(gapminder)
head(gapminder)
tail(gapminder)
```
Además, podés buscar ayuda sobre este paquete y así tener más información sobre qué es cada variable:

```r
?gapminder
```

Las variables que incluye son país (`country`), continente (`continent`), año (`year`), expectativa de vida (`lifeExp`), población (`pop`) e ingreso per cápita en dólares (`gdpPercap`). Una función útil para conocer los nombres de las columnas de un conjunto de datos es a través de la función `names()`. 
```r
names(gapminder)
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/names_gapminder.png" align="center" width="70%"></a>

Otra función muy útil para conocer nuestros datos es `summary()`.
```r
summary(gapminder)
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/summary.png" align="center" width="80%"></a>

### Filtrar casos

Tal como vimos más arriba, la función `filter` sirve para seleccionar registros (o filas) a partir de un determinado criterio. Al igual que buscamos nombres de personas en `babynames`, acá podemos buscar los datos de algún país: 

```r
gapminder %>% 
    filter(country == "China")
```

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/filter_china.png" align="center" width="60%"></a>

¡Es impresionante cómo aumentó el PBI y la expectativa de vida en China en el último medio siglo!  

La función `filter` admite más de un criterio de filtrado. Por ejemplo, si quisiéramos saber qué países tuvieron un PBI per cápita menor que 1000 dólares durante 2007, podríamos hacerlo así:

```r
gapminder %>% 
    filter(year == 2007, gdpPercap < 1000)
```
Es decir, le estamos pidiendo a R que:

* tome el objeto `gapminder`
* a continuación (` %>% `)
* filtre las filas que cumplan con dos criterios: año `==` 2007 y PBI `<` que 1000 dólares.

La mayoría de los países que tuvieron un PBI tan bajo ese año se encuentran en África: 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/gapminder_2007_PIB.png" align="center" width="60%"></a>


Existe muchas otras formas de crear criterios de filtrado. Veamos un último ejemplos que nos servirá para practicar la creacion de objetos. 

En los ejemplos anteriores sólo consideramos un valor por variable para filtrar (por ejemplo, que país fuera `==` a China). ¿Cómo podríamos hacer una selección que incluya más países?

Imaginá que sólo nos interesan los datos de Sudamérica. La variable `continent` considera a las tres Américas como un único continente, así que no podemos seleccionarlas usando ese valor. 

Lo que podríamos hacer es crear un vector con todos los países de América del Sur que están en `gapminder`. Un vector se puede pensar como una fila de elementos (en este caso el nombre de los países) ordenados uno detrás de otro. Se puede decirle a R que use el vector como criterio de selección, así:

```r
gapminder %>% 
    filter(country %in% 
                c("Argentina", "Bolivia", "Brazil", 
                  "Chile", "Colombia", "Ecuador", 
                  "Paraguay", "Peru", "Uruguay", "Venezuela"))
```
    
Lo que le estamos pidiendo a R es que

* tome el objeto `gapminder`
* luego (` %>% `)
* que filtre las filas en que el valor de la variable/columna `country` se encuentre en (`%in%`) el conjunto de nombres que indicamos a continuación. Esos nombres los agrupamos formando un vector usando la función `c()` (concatenar).

¡Listo!

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/gapminder_latam.png" align="center" width="75%"></a>


Recuerda que también podés agregar `View()` al final del código para ver tu selección en una ventana distinta. 

```r
gapminder %>% 
    filter(country %in% 
                c("Argentina", "Bolivia", "Brazil", 
                  "Chile", "Colombia", "Ecuador", 
                  "Paraguay", "Peru", "Uruguay", "Venezuela")) %>% 
    View()
```

Si esta selección de casos nos interesa y tenemos intención de seguir usándola, nos conviene guardarla como un nuevo objeto usando el operador `<-`. Esto permite que no tengamos que volver a escribir un criterio de filtrado tan largo cuando queramos volver a trabajar con esos datos.

```r
gapminder_sudamerica <- gapminder %>% 
    filter(country %in% 
                c("Argentina", "Bolivia", "Brazil", 
                  "Chile", "Colombia", "Ecuador", 
                  "Paraguay", "Peru", "Uruguay", "Venezuela"))
```

Ahora el objeto apareció en nuestro Global Environment. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/environment_gap_sudamerica.png" align="center" width="50%"></a>


IMPORTANTE: muchas veces agregamos `View()` al final de un bloque de código para ver los datos en una ventana distinta. Es muy importante no incluir esa función cuando creamos un nuevo objeto para que el código haga lo que esperamos. 


#### ¿Y si quisiera guardar esos datos en mi computadora en lugar de en el Global Environment? 

El paquete `readr`, que es parte del Tidyverse, tiene funciones muy útiles para importar y exportar archivos. En este caso, utilizaremos `write_csv()` para guardar en nuestra computadora los datos de Gapminder para Sudamérica. Tenemos dos opciones.

Si ya creamos el objeto, podemos indicar su nombre como primer argumento dentro de la función. El segundo argumento es el nombre que queremos que tenga el archivo creado.

```r
write_csv(gapminder_sudamerica, "gapminder_sudamerica.csv")
```

Al ejecutar el código, aparecerá en la carpeta de nuestro proyecto el nuevo archivo. 

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/objeto_gapminder_sudamerica.png" align="center" width="50%"></a>


Otra opción sería incluir la función `write_csv()` al final de nuestro código, es decir, como una siguiente acción en la cadena de comandos que le dimos a R:

```r
gapminder %>% 
    filter(country %in% 
            c("Argentina", "Bolivia", "Brazil", 
              "Chile", "Colombia", "Ecuador", 
              "Paraguay", "Peru", "Uruguay", "Venezuela")) %>%
    write_csv("gapminder_sudamerica.csv")
```
En este último caso, no indicamos el primer argumento, ya que los datos que se deben considerar para guardar el objeto se generan en los pasos previos del código.


### Ordenar los casos

Supongamos que nos interesa conocer la expectativa de vida de América del Norte, Centro y Sur. El último registro que contiene la base es de 2007, así que simplemente podríamos revisar los datos aplicando ese filtro y agregando View al final para mirarlos todos en una nueva pestaña:

```r
gapminder %>% 
    filter(year == 2007, continent == "Americas") %>% 
    View()
```
El problema que tenemos es que los datos aparecen ordenados alfabéticamente, es decir, según la variable `country`. Una manera de resolver esto es indicando explícitamente a partir de qué variable queremos que se ordenen. Para eso, podemos utilizar la función `arrange()`. 

```r
gapminder  %>% 
    filter(year == 2007, continent == "Americas") %>%
    arrange(lifeExp)
```

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/arrange_lifeExp.png" align="center" width="80%"></a>


¡Ahora es más fácil mirar los resultados! Podemos ver que, en la región en 2007, Haití, Bolivia y Trinidad y Tobago son los países con menor expectativa de vida. 

Por defecto, `arrange()` organiza los datos de menor a mayor. ¿Y si quisiéramos ver el orden inverso?. En ese caso, tendríamos que indicar que el orden que nos interesa es el descendiente: `desc()`. Explicitamos esto dentro de la función `arrange()`:

```r
gapminder %>% 
    filter(year == 2007, continent == "Americas") %>%
    arrange(desc(lifeExp))
````
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/desc_lifeExp.png" align="center" width="80%"></a>

Un error habitual (muy habitual) es que se nos olvide algún paréntesis en nuestro código, sobre todo cuando, como en el caso anterior, comenzamos a agregar una función dentro de otra. Al agregar `desc()` podríamos haber olvidado el paréntesis extra que teníamos que agregar al final y hubiese ocurrido esto en la consola:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/R_espera_mas.png" align="center" width="80%"></a>

En vez del signo `>`, que es el que nos indica que R terminó de ejecutar la acción anterior y que está dispuesto a aceptar nuevos comandos, aparece un `+`. Lo que quiere decir R con esto es que algo falta en el código que acabamos de ejecutar. 
Uno de los aspectos positivos de RStudio es que para que no ocurra esto, tratará de advertirnos sobre este tipo de errores cuando pueda identificarlos. Si hubiéramos olvidado el último paréntesis en nuestro script, RStudio habría hecho esto:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/error_parentesis.png" align="center" width="60%"></a>

Al costado izquierdo de la línea en que identifica el error, habría aparecido una alerta. 

Olvidar un paréntesis o una coma es uno de los errores más habituales, así que es muy útil que RStudio nos ayude a indentificar problemas en nuestro script. 

### Agrupar

Más arriba vimos que la función `summarize()` nos permite crear una tabla que resume información de acuerdo a algún criterio. Por ejemplo, si quisiéramos conocer el promedio de la variable expectativa de vida para el año 2007, podríamos utilizar el siguiente código:

```r
gapminder %>% 
    filter(year == 2007) %>% 
    summarize(mean(lifeExp))
```
El resultado es 67 años. Este dato no es muy informativo respecto de las diferencias que podrían existir por continente. ¿Cómo podríamos desagregar esa información? Para estos casos, la función `group_by()` resulta muy útil:

```r
gapminder %>% 
    filter(year == 2007) %>%
    group_by(continent) %>% 
    summarize(mean(lifeExp))
```
Lo que les estamos pidiendo a R es que:
* tome el objeto `gapminder`, luego (` %>% `)
* que filtre (` filter `) los casos del año 2007, luego (` %>% `)
* que agrupe (` group_by `) los casos de acuerdo a la variable continente, y luego (` %>% `)
* que haga un resumen (` summarize `) de la información que sale de calcular la media de la variable expectativa de vida (` mean(lifeExp) `). 


<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/group_by.png" align="center" width="80%"></a>

Esto nos permite tener una mejor idea de las diferencias que existen en la expectativa de vida de las distintas regiones: África está muy por debajo de las otras.
 
### Crear nuevas variables

Muchas veces necesitamos agregar a nuestros datos nuevas variables. La función que nos permite hacer eso es `mutate()`. Veamos un ejemplo. 

La variable gdpPercap mide el ingreso per cápita en dólares. ¿Cómo podríamos agregar una variable a nuestros datos que incluya el valor en otra moneda? Una opción sería multiplicar la variable que ya tenemos por el valor actual de conversión de esa moneda. Para hacer esto, utilizaremos la función `mutate`. Al usarla, indicamos el nombre que queremos que tenga la nueva variable y qué valor queremos que tenga. Como lo que queremos es asignar un valor, usaremos `=`: `mutate(nombre_nueva_variable = su_valor)`.

El siguiente es un ejemplo chileno (como la autora original de este tutorial). Filtraremos los datos de Chile, donde el valor de conversión del dólar es, por ejemplo, de 595 pesos. 

```r
gapminder %>% 
    filter(country == "Chile") %>% 
    mutate(PIB_pesos = gdpPercap * 595)
```
Lo que le estamos pidiendo a R es que 

* tome el objeto gapminder, luego
* filtre los casos correspondientes a Chile, luego 
* cree una variable llamada `PIB_pesos`, cuyo valor sea el de la variable `gdpPercap` multiplicado por 595 (el valor del dólar en pesos chilenos).

Con la operación que acabamos de hacer sólo creamos momentáneamente la variable para la sección de datos que filtramos. Para poder guardarla de manera definitiva tendríamos que crear un nuevo objeto que la incluya. Lo llamaremos `gapminder_CL`.

```r
gapminder_CL <- gapminder %>% 
    filter(country == "Chile") %>% 
    mutate(PIB_pesos = gdpPercap * 595)
```

### Graficando los datos

Una parte importante del análisis de datos es visualizarlos en distintos gráficos. Con cualquiera de los objetos que contienen datos podríamos hacer gráficos usando el paquete `ggplot2` dentro del Tidyverse. 

`ggplot` propone una gramática de gráficos que se construyen por capas. Para hacer un gráfico usando `ggplot` tenemos que indicar cuáles son los datos, qué tipo de gráfico vamos a usar y cómo se van 'mapear' las variables (eje x e y, en este caso).

```r
ggplot(data = gapminder_CL) + 
    geom_line(mapping = aes(x = year, y = gdpPercap))
```

Vas a ver que este gráfico aparece en _Plots_ en la ventana de abajo a la derecha de RStudio.

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/plot1.png" align="center" width="80%"></a>

En este caso, el signo `+` su usa para agregar capas a nuestro gráfico. `ggplot()` sólo establece un sistema de coordenadas sobre el cual se agrega el gráfico propiamente dicho. 

Es muy importante que el signo `+` esté en la misma línea de la función que lo antecede para que el código funcione.

Probá ver lo que sucede cuando ejecutás:

```r
ggplot(data = gapminder_CL) 
    + geom_line(mapping = aes(x = year, y = gdpPercap))
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/ggplot_error.png" align="center" width="70%"></a>

Vas a notar que en la ventana de abajo a la derecha en _Plots_ desaparece el gráfico anterior y aparece:

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/plot2.png" align="center" width="60%"></a>

Cuando el signo `+` no queda en la misma línea que la función que lo antecede sólo se genera la primera capa del gráfico. `ggplot()` sólo genera un cuadro gris.

Tanto `ggplot` como `geom_line` son funciones y, como tales, si se respeta el orden de los argumentos, se puede simplificar el código de la siguiente forma:

```r
ggplot(gapminder_CL) +
    geom_line(aes(year, gdpPercap))
```

Como explicábamos para `head` antes, `ggplot` esperará que lo primero que se indique sean los datos. Por su parte, `geom_line` espera que el primer y segundo argumento sean las variables del eje x e y, respectivamente. Nuevamente, siempre que se respete el orden de los argumentos, se puede simplificar el código.

Notá que encima del gráfico hay dos flechas. Probá hacer clic en la que apunta para la izquierda.

<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/arrows.png" align="center" width="30%"></a>

La función `ggplot` también puede incluirse dentro del código que utilizamos para filtrar la base de datos. Es decir, no tenemos por qué crear un objeto distinto con los datos de Chile para poder graficar sólo esos datos. 

```r
gapminder %>% 
    filter(country == "Chile") %>% 
    ggplot() + geom_line(aes(year, gdpPercap))
``` 
    
La única diferencia es que en `ggplot` no es necesario indicar cuáles son los datos porque ya que lo indicamos al principio del código.

Al ejecutar ese último código va a parecer que no se ejecutó nada. Sin embargo, si usás las flechas para navegar los gráficos que fuiste generando, notarás que tenés dos gráficos idénticos luego del cuadrado gris que apareció en pantalla cuando pusimos el signo `+` en la línea siguiente a la de `ggplot()`.


### Cambiar el nombre de una variable

Más arriba creamos un nuevo objeto filtrando los casos sudamericanos. Si seguís en la misma sesión, el objeto `gapminder_sudamerica` debería estar aún en tu Global Environment. Si no, podés volver a ejecutar el código con que lo creamos o, si guardaste el archivo csv, podés cargarlo usando la función inversa a `write_csv()`: `read_csv()`.

Los archivos que guardan datos en formato de texto plano y cuyas columnas se separan por comas son del tipo "separados por coma" y suelen terminar en `.csv` (abreviatura de comma separated values). 

Probemos usar `read_csv()`. Cerremos RStudio. Luego, desde el directorio donde armamos el proyecto, volvamos a abrir este proyecto haciendo clic en el archivo .Rproj. Ejecutemos las líneas de código que comienzan con `library` para cargar los paquetes con los que estábamos trabajando nuevamente. Si quisiéramos importar el archivo `gapminder_sudamerica.csv` para recuperar lo que hicimos en la sesión anterior bataría con ejecutar:

```r
gapminder_sudamerica <- read_csv("gapminder_sudamerica.csv")
```
Lo que le estamos pidiendo a R con esta función es que 

* al objeto llamado `gapminder_sudamerica`
* le asigne como valor (`<-`)
* los datos incluidos en el csv `gapminder_sudamerica.csv`

(NOTA: Si ejecutás este código y ya tenés un objeto llamada `gapminder_sudamerica` en tu Global Environmet, lo que hará R será sobreescribirlo).

Esa es la forma de importar datos en R. Le pedimos que lea un archivo y asigne los datos que ahí encuentre a un objeto en nuestro entorno de trabajo. Lo más importante a tener en cuenta es que al importar esos datos __el archivo original no se modifica__. Es decir, todas las acciones que realicemos en R solo afectarán al objeto que creamos en nuestra sesión, no al archivo .csv que está en tu computadora. La única forma de alterarlo sería que sobreescribiésemos el archivo con `write_csv()`. 

Hay muchísimas opciones más para la importación de este tipo de archivo (y también de casi cualquier otro tipo de archivos con datos) en R.

Que R no altere el archivo original no solo es bueno porque evita que, por error, arruinemos nuestros datos, sino también porque hace más transparente y reproducible nuestro trabajo. Cualquier persona con el archivo original y nuestro script puede reconstruir el análisis que hicimos. 

Si ya tenés el objeto `gapminder_sudamerica` en tu Global Environment, podemos seguir. 

En estos datos todos los nombres de las variables se encuentran en inglés. Podemos chequear eso con una función que vimos más arriba: `names()`:

```r
names(gapminder_sudamerica)
```
<a href="url"><img src="https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/names_gapminder_sudamerica.png" align="center" width="85%"></a>

Para cambiar los nombres de las variables podemos utilizar la función `rename()` (_renombrar_). Para cada variable a la que queremos cambiar el nombre, lo que hacemos es indicar el nombre nuevo y luego el valor que tendrá, así: `nombre_nuevo = nombre_actual`. Si quisiéramos cambiar de forma permanente los nombres de todas las variables, tendríamos que sobreescribir el objeto y aplicar esta función:

```r
gapminder_sudamerica <- gapminder_sudamerica %>% 
    rename(pais = country, continente = continent, 
           anio = year, expec_vida = lifeExp, 
           poblacion = pop, PIB_percap = gdpPercap)
```
¡Listo! Ahora los nombres de las variables están traducidos. Para chequearlo, luego de ejecutar el código anterior, podés volver a aplicar la función `names()` o podés revisar los datos con alguna de las funciones que vimos antes, como `View()`, `str()` o `head()`.

### Seleccionar variables

Antes de volver a guardar nuestro objeto como un archivo `.csv`, haremos un último cambio. Nuestros datos sólo incluyen los datos de Sudamérica, por lo que la variable `continent` es poco informativa. Reescribiremos el objeto sin incluirla. Necesitamos, entonces, una función que nos permita seleccionar columnas. 

Como en el Tidyverse todo trata de ser transparente, la función se llama `select()` (_seleccionar_). Cuando usamos esa función, lo que indicamos en su interior es el nombre de las columnas que queremos seleccionar. Veamos un ejemplo. Agregaremos `View()` al final del bloque de código para ver el resultado:

```r
gapminder_sudamerica %>% 
    select(pais, anio, expec_vida, poblacion, PIB_percap) %>% 
    View()
```
Perfecto. Lo que hicimos en este caso fue indicar el nombre de las columnas que queremos mantener.

Pero más que mantener columnas, lo que queríamos hacer era deshacernos de `continente` y eso podemos hacerlo de una manera mucho más rápida: diciéndole a R qué es lo que no queremos conservar. Así:

```r
gapminder_sudamerica %>% 
    select(-continente) %>% 
    View()
```
El resultado es el mismo. Al anteponer un `-` al nombre de la columna, le decimos a R que queremos conservar todas excepto esa. Es muy práctico si nuestra base tiene muchas variables y solo queremos eliminar unas pocas.

Guardemos ahora nuestro objeto:

```r
gapminder_sudamerica %>% 
    select(-continente) %>% 
    write_csv("gapminder_sudamerica.csv")
```

Si no querés que sobreescriba el que ya tenías (con los nombres de las variables en inglés) ponéle otro nombre al archivo.

## Eso es todo por ahora

¡Hay mucho más que aprender! ¿Por dónde seguir?

* Si sabés inglés, la sugerencia es trabajar con el libro de Garrett Grolemund y Hadley Wickham [R for Data Science](https://R4DS.had.nz.co). Con ese libro se puede profundizar en lo cubierto en este tutorial, pero sobre todo apropiarse de un proceso de trabajo con datos con un enfoque moderno y en constante actualización.

* RStudio tiene síntesis muy útiles llamadas "cheatsheets" que se pueden encontrar [aquí](https://www.rstudio.com/resources/cheatsheets/). Algunas de ellas cuentan con traducciones al español (para encontrarlas en la página de RStudio tipeá `Ctrl + F` y luego `Spanish` en la caja de búsqueda tu navegador).

* Un tutorial sobre aspectos básicos de R usando mayormente la gramática tradicional de R base puede encontrarse en este tutorial elaborado para un curso de [Fundación Sadosky](http://www.fundacionsadosky.org.ar/mailings/pcd/intro.html). También están disponibles las clases [1](http://www.fundacionsadosky.org.ar/pcd-salud/introduccion_R.pdf), [2](http://www.fundacionsadosky.org.ar/pcd-salud/analisis_exploratorio.html) y [3](http://www.fundacionsadosky.org.ar/pcd-salud/dataviz.pdf) del curso "Análisis de Datos en Salud" organizado por Fundación Sadosky en 2016.

* R es un lenguaje de programación de código abierto con una comunidad muy activa que constantemente aporta materiales nuevos. Varios usuarios hispanohablantes han empezado a generar una [lista de recursos en español](https://github.com/rladies/recursos_en_espanol) que poco a poco va creciendo. 

## Tarea para el hogar

En el curso de Claudia Coeli, se usará los siguientes paquetes `arules`, `summary`, `epiDisplay`, `psych`, `gridExtra`, `ggplot2`, `GGally`, `fpc`, `cluster`, `NbClust` y `stats`. El paquete `stats` viene con el R base y no hace falta instalarlo. El resto de los paquetes es posible que necesites instalarlos. Podés hacerlo usando este comando:

```r
install.packages(c("arules", "summary", "epiDisplay", "psych", "gridExtra", 
                   "ggplot2", "GGally", "fpc", "cluster", "NbClust"))
```
En este código, en lugar de instalar los paquetes uno a uno como hicimos al principio del curso, los concatenamos usando la función `c()` y los pedimos todos juntos. Así nos ahorramos unas líneas de código.

Cuando comience el taller la semana que viene, podés reutilizar este código cambiando `install.packages` por `library` para cargar los paquetes y así ternelos disponibles en la sesión de R que abras ese día.

Es **muy importante** que instales los paquetes **antes** de venir al taller. Caso contrario podría suceder que no tengas las herramientas para aprovechar el taller.
