---
title: Creando scripts - Parte III
subtitle: Escribe menos utilizando scripts
date: 25-05-2019
---

Ahora que ya has comenzado a utilizar la terminal, te habrás dado cuenta de algunos códigos que sueles escribir una y otra vez. Por ejemplo para hacer una página web sencilla, necesitas crear un mínimo de archivos y carpetas. Hoy aprenderás cómo hacer un script, que resuelva este problema.

## Definiendo el problema

Antes de comenzar a escribir un programa, código... lo primero que se tiene que hacer, es plantearse cual es el problema, qué es lo que queremos lograr y cómo lo vamos a hacer.

**Problema:** No queremos tener que escribir tanto cada vez que vamos a empezar un proyecto.  
**Objetivo:** Hacer un pequeño código que cree una carpeta para nuestro proyecto, que contenga los archivos que necesitamos para comenzar.

Sobre el como... Cuando voy a comenzar algo muy sencillo, utilizo la siguiente estructura:

```

Carpeta-|
	|- index.html
	|-css
	|  |- index.css
	|
	|- js


```

Comenzaremos nuestro script escribiendo en nuestra terminal `vim script.sh`.

**vim** es un programa que nos permite editar archivos de texto directamente desde nuestra terminal. Vim es un tema muy extenso, que merece su propia serie de posts, pero veremos en esta ocasión, lo más básico.

Vim es lo que se llama un editor modal. Cuando entras, se encuentra en modo Normal. En este modo es donde se pueden utilizar diferentes atajos y comandos propios de Vim, así como comandos directos a la consola.

Para empezar a escribir, debemos presionar la tecla `i`. Con esto entramos a "EDIT" mode. En el cual podemos escribir casi como en un programa cualquiera. Vim no acepta que utilicemos el mouse. Por ahora, vamos a utilizal las flechas del teclado para movernos.

Lo primero que tenemos que poner en nuestro archivo es un breve comentario del programa con el que se debe abrir el archivo.

```

#!/bin/bash

```

Después de esto, todo lo demás es como si escribieras directo sobre to temrinal.

```

#!/bin/bash

touch index.html
mkdir css
mkdir js
touch css/index.css
touch js/index.js


```

Sólo nos falta un detalle. Necesitamos recibir el argumento que indique el nombre de la carpeta en la que irán estos archivos y carpetas. Para eso, tendermos que utilizar `$@`:

```

#!/bin/bash

mkdir $@
cd $@

touch index.html
mkdir css
mkdir js
touch css/index.css
touch js/index.js

```

Eso es todo lo correspondiente a escribir nuestro *script*. Ahora para guardar, tenemos que entrar a modo "NORMAL". para ello utilizamos la tecla `ESC`. Ahora escribimos `:w`. Los dos puntos se utilizan cuando se quiere insertar un comando propio de Vim. La `w` es la que le indica que tiene que guardar el archivo. Ahora para salir utilizaremos `:q` y con esto regresamos a nuestra consola. Para guardar y salir en un solo comando se puede escribir `:wq` también.

Antes de poder utilizar nuestro pequeño programa, tenemos que darle permiso de ejecución. Para esto utilizaremos el comando `chmod +x script.sh`. Y ahora ya podemos utilizar nuestro programa, escribiendo `./script.sh super-proyecto`. Si utilizamos `ls`ahora podemos ver que se creado la carpeta `super-proyecto` y si navegamos dentro de ella, podremos ver que tiene los archivos y carpetas que queríamos.

Si estuviste atento, te habrás dado cuenta de que al utilizar script, no hemos cambiado de carpeta, a pesar de que dentro del script, cambiamos a la carpeta de nuestro proyecto. Un script puede navegar por varias carpetas, pero cuando termine de ejecutarse, nos regresará a carpeta desde la que lo llamamos.

Si queremos utilizar el programa que creamos desde otra carpeta, tendremos que escribir toda la dirección. Suponiendo que este progrma lo creamos en nuestra carpeta de usuario, si escribimos `~/script.sh` podremos utilizarlo desde cualquier carpeta. Hay formas de que podamos darle un "apodo" al script para que podamos ejecutarlo sin necesidad de escribir su ubicación completa, pero dejaremos esa parte, para la próxima ocasión.
