---
title: Hazla tuya... la terminal
subtitle: mv, .bashrc, .bash\_profile, alias
date: 09-06-2019
---

El post pasado hicimos un script llamado `script.sh`que utilizamos para crear una carpeta, con la estructura que necesitamos para hacer una página web. Ahora en este post colocaremos el archivo en una carpeta más adecuada y comenzaremos a personalizar un poco como funciona nuestra terminal.

## mv

Primero hacemos una carpeta llamada scripts:

```
mkdir scripts
```

Además de mover el archivo, queremos cambiar el nombre. Utilizaremos el comando `mv`para mover el archivo primero.

```
mv script.sh scripts
cd scripts
ls
```

Como se puede ver, `mv` acepta dos comandos. El primero es el nombre del archivo que queremos **m**o**v**er y el segundo es la ubicación a la que queremos moverlo.

Pero `mv` también tiene otro uso: renombrar archivos. Cuando este comando no encuentra la ubicación dada en el segundo parámetro, entiende que el segundo parámetro es el nuevo nombre.

```
mv script.sh pagina.sh
ls
```

Ahora podemos ver que ya no hay ningún archivo llamado `script.sh` y que en su lugar está el archivo `página.sh`.

Ahora tenemos un nuevo problema. Para que se ejecute este script desde cualquier carpeta que estemos, necesitamos escribir `~/scripts/pagina.sh`y nosotros somos muy flojos para eso, por lo que vamos a crearle un "apodo" que nos ayude a escribir menos.

## .bashrc y .bash\_profile

Estos dos archivos suelen encontrarse en nuestra carpeta de inicio. Así que volvemos allá y escribimos ls -A. Esto nos mostrará los archivos y carpetas oculatas en nuestra carpeta. Estos archivos en sistema Linux llevan un punto al inicio de su nombre. Puede que no tengas estos archivos en un inicio, pero no importa. Porque el punto de estos archivos es personalizar la forma en la que usas la computadora.

Existe mucha gente que comparte estos archivos con los demás para que puedan tomar ideas de como mejorar su flujo de trabajo. Sin embargo, en muchas ocasiones se puede tener información delicada en este archivo que se prefiere mantener lejos de los ojos fizgones.

Dado que estoy en MacOs, la forma más común de utilizar estos archivos es simplemente agregar nuestros *alias* y *funciones* a `.bash_profile`. Los que utilizan distribuciones de Linux utilizan `.bashrc`. En lo personal yo utilizo `.bashrc` e invoco con `source .bashrc` todo en `bash_profile`. Me funciona cuando utilizo **tmux** pero desde que comencé a utilizar iTerm2, no le he dado el mismo uso. Aunque de vez en cuando utilizo algún servidor Linux, en el que es bastante conveniente seguir teniendo esta modificación.

Como estamos empezando aún y no vamos a utilizar **tmux** vamos a poner los alias en `.bashrc`. Ya más adelante haremos una explicación de la diferencia de estos dos archivos.

## alias

Un alias es un "apodo" a un código relativamente sencillo que se utiliza, regularmente, para evitarnos los problemas de tener que escribir muchas letras o para hacer que un comando que utilizamos regularmente, se comporte de una manera distinta.

Primero, haremos el **alias** de nuestro script "pagina.sh".

```
echo alias pagina="cd ~/scripts/pagina.sh" >> .bash_profile
```


Para editar estos archivos podemos utilizar **vim** como la vez pasada o podemos simplemente direccionar el texto al archivo. Como acabamos de hacer.

Si intentas escribir `pagina`en tu CLI ahora mismo, no va a funcionar. Primero tiene que enterarse la terminar no sólo de que ya existe un `.bash_profile` sino también que se le han hecho modificaciones. La forma más comoda cuando se está comenzando es cerrando la terminal y volviéndola a abrir. Otra forma, en mi opinión, mejor. Es con el comando `source` que mencionamos como una curiosidad allá arriba. No vamos a hablar mucho de este comando. Pero digamos que es como decirle a la terminal "Aquí están las nuevas instrucciones".

```
source .bash_profile
```

De esa manera, ya estará nuestro alias listo para utilizarlo. De tal manera que el código de abajo debería mostrarnos que hemos creado una carpeta llamada 'test' con todo el contenido que habíamos indicado la vez pasada.

```
pagina test
```

Hay muchos **alias** que puedes utilizar para agilizar tu flujo de trabajo. Abajo te dejo algunos ejemplos. Sólo recuerda que el apodo no puede ser de más de una palabra de largo. Yo recomiendo que utilices puras letras, para ahorrarte problemas, puedes utilizar número, pero no comiences el **alias** con un número. Recuerda que entre el apodo, el signos de igual y las comillas, no puede haber ningún espacio. Escribe un alias por línea. Con eso deberías estar bien.

```
alias v="vim"
alias .."cd .."
alias clear="cl"
alias la="ls -A"
```

No olvides que los apodos tienen que ser fáciles de recordar. Si no los puedes recordar, no los uses.

Sigue programando.
