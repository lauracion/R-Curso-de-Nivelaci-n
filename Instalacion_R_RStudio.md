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
Es esencial que todo lo que sigue a estas líneas se haga antes de concurrir en forma presencial al Curso de Nivelación. Caso contrario, es posible que no puedas practicar en tu computadora los pasos que seguirán durante el curso.

_________

## Instalación de R y RStudio

En este curso utilizaremos R a través del IDE RStudio. 

¿Qué es un IDE? IDE es el acrónimo de *Integrated Development Environment* (*Entorno de Desarrollo Integrado*). Esto quiere decir que RStudio es una aplicación que nos entrega herramientas para hacer más fácil el desarrollo de proyectos usando R.

Para poder instalar R y RStudio, seguí los siguientes pasos:

- Descargá R desde https://cran.r-project.org/. Debés elegir la opción que corresponda, según tu sistema operativo.
- Instalá R en tu computadora, tal como lo hacés con cualquier programa. 
- Una vez que R quedó correctamente instalado, descargá RStudio desde https://www.rstudio.com/products/rstudio/download/. Eligí la primera opción, es decir, "RStudio Desktop Open Source License" (gratuita). 
- Instalá RStudio en tu computadora, tal como lo haces con cualquier programa. 

Para un paso a paso que incluye imágenes de este proceso de instalación podés ir a [este archivo](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/Instalacion_R_RStudio.pdf). 
Si quedó todo bien instalado, cuando abras RStudio deberías ver algo que se parece a esto:

![](https://github.com/lauracion/R_Curso_de_Nivelacion/blob/master/images/rstudio.png)

En este curso usaremos la última versión de R y RStudio, así que si tenés instalada una versión previa, puede que algunas cosas se vean un poco distintas.

IMPORTANTE: Si aparece algún error durante este proceso, lo más probabable es que sea por alguna configuración de tu sistema operativo. En ese caso, la mejor manera de buscar una solución es copiar el error que arroja R, pegarlo en, por ejemplo, Google y ver cómo alguien que se enfrentó a eso antes lo resolvió. Si no lográs solucionarlo, veremos problemas que hayan surgido personalmente durante el transcurso del curso.

## Instalación de los paquetes de R que usaremos

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
Si no tienes la última versión de R, puede que aparezca un "Warning" durante la instalación, que te avisa que el paquete fue construido bajo otra versión de R. Un "Warning" es distinto a un error: R ejecuta el código que le pidas, pero advierte que no todo puede resultar como esperas. Cuando aparece un error, en cambio, el código no se ejecuta. 
