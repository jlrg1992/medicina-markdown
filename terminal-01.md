---
title: Conociendo la terminal - Parte I
subtitle: Introducción, mkdir, pwd, cd, ls, open, rm
date: 21-05-2019
---

En este breve post voy a explicar los comando más básicos que se deben conocer para comenzar a trabajar con la terminal. Vamos a trabajar con bash. Sobre todo esta serie va a estar enfocada para los usuarios de MacOs. Sin embargo, vamos a ser lo más apegados posible al estándar POSIX.

## ¿Qué es la terminal?

Utilizar la terminal es como mensajearse con tu computadora. Tu le das una indicación escrita y ella responde, generalmente, con un montón de texto. Formalmente, la terminal es una interface que nos sirve para comunicarnos con nuestra computadora.

Algunas veces nos encontraremos con el termino `CLI` (Command-line Interface). Esto se refiere a una interface para comunicarnos con un programa. Nosotros utilizaremos bash. Éste es un programa que corre en CLI's de sistemas operativos basados en Unix, como es el caso de MacOs.

## ¿Para qué aprender a utilizar la terminal?

¿Por qué querríamos aprender toda una serie de comandos, cuando los sistemas operativos modernos tienen muy buenas interfaces de usuario gráficas (GUI)? Hay varias aplicaciones, pero la mayoría de las que se suelen escuchar son sólo útiles para los programadores profesionales. El motivo por el que yo utilizo la terminal es que es más fácil de analizar grandes cantidades de información y me permite hacer cosas, que los programas, no tienen contemplado. Esto, sin olvidar que a través de la creación de *scripts* y modificando la configuración inicial, se puede llegar a automatizar mucho de lo que solemos hacer en una computadora.

## Tus primeros comandos

Para comenzar vamos a abrir la terminal. En MacOs la puedes abrir con las teclas `cmd + espacio` entonces aparecerá el buscador Spotlight, donde con escribir `Term`y un `enter` abrirá la aplicación de terminal.

### mkdir

Lo primero que vamos a hacer es crear una carpeta con el comando `mkdir programa` y damos `enter`. Con esto ya hemos creado nuestra primera carpeta llamada "programa".

### ls

¿Cómo podemos ver el contenido de nuestra carpeta? Con el comando `ls`. Si lo escribes en la terminal (todos los comandos se finalizan con enter), podrás ver una lista carpetas y entre ellas nuestra carpeta "programa".

### pwd

¿Pero dónde estoy, no recuerdo haber visto estas carpetas? Cuando inicias tu terminal (en MacOs) inicias en la carpeta de usuario. Si en algún momento llegas a perderte y no sabes en qué carpeta estás o como llegaste ahí, puedes usar el comando `pwd` este comando imprime en la terminal tu ubicación. Si te fijaste, cuando utilizaste el comando `ls`, en medio del conenido, se veía la carpeta Desktop, la carpeta Downloads y otras a las que regularmente se accede mediante enlaces directos o através de la pestaña de favoritos.

### cd

Para moverte de una carpeta a otra se utiliza `cd`(change directory). Este comando acepta (igual que mkdir) un argumento, que sería la carpeta a la que quieres ir. Entremos a la carpeta "Desktop" con `cd Desktop`. Si utilizas pwd, podrás ver que te encuentras ahora en la carpeta de Desktop.

¿Y cómo regreso a la carpeta que estaba antes? Si te fijas con `pwd` debes de haber recibido una respuesta como `/Users/tu-usuario/Desktop` para regresar a la carpeta "tu-usuario" hay tres maneras.

```
// La primera:
cd /Users/tu-usuario

// La segunda:
cd ~
// ~ es una forma abreviada de referirse a tu carpeta de usuario.

// La tercera:
cd ..
// Los dos puntos ".." son una forma de referirse a la carpeta "arriba" de la que ocupas en el momento
```

Si sólo escribieras un punto `cd .` te quedarías en la misma carpeta. Porque el punto se utiliza para referirse a la carpeta en la que te encuentras actualmente.

### open

El comando `open` se utiliza para abrir un archivo con el programa determinado por el sistema operativo. Claro que el programa determinado se puede modificar en tus preferencias del sistema. Un ejemplo son las carpetas. El programa que utiliza Mac para abrir las carpetas es Finder. Entonces si utilizamos `open .` Abrirá la carpeta en la que estemos en el Finder, como suele verlo mayoría de la gente.

### rm

Como última tarea para este post vamos a eliminar nuestra carpeta "programa" con el comando `rm`. Éste tiene la peculiaridad de que no manda lo eliminado al basurero, sino que lo elimina completamente. Si quisiera eliminar un archivo bastaría con escribir `rm nombreDelArchivo` pero como lo que vamos a eliminar es una carpeta, necesitamos darle unas indicaciones extras.

```
// Primero vamos a asegurarnos de estar en la carpeta correcta. O sea, una carpeta arriba. En este caso, la carpeta de usuario

cd ~ 

// Luego vamos a utilizar rm con la indicación rf.

rm -rf programa
```

Es importante ver el guión `-` que se utiliza para esta indicación extra. La "r" se refiere a que elimine de manera recursiva. Esto quiere decir que elimine también el contenido y si en ese contenido hay carpetas, también el contenido de esas carpetas y así consecutivamente. La "f" es para "forzar" el comando. Es como cuando tu mamá te dice algo en tono serio para que no dudes en hacerlo.

Bueno, con esto terminamos nuestra primera introducción a la terminal. No se olviden que la mejor manera de aprenderse todos estos comandos es utilizándolos, así que busquen pretextos para buscar sus archivos desde la terminal y abrirlos. Hasta el próximo post.
