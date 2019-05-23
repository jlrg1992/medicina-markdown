---
title: Conociendo la terminal - Parte II
subtitle: touch, \>, \>\>, echo, cat
date: 21-05-2019
---

Ahora es hora de comenzar a manipular algunos archivos de texto.

## touch

`touch` es un comando que permite crear un archivo vació. Por lo que si utilizas el siguiente código, quedarás con una carpeta nueva y dentro de ella un archivo sin contenido.

```
mkdir lecc-02
touch lecc-02/archivo.txt
```
## echo

Antes de poner contenido en nuestro archivo, hay que conocer el comando `echo`. Este comando muestra en la terminal, lo que le pases como parámetro.

```

echo "Hola a todos"

// Hola a todos

```

## \>\>

¿Pero como puedo poner contenido en un archivo? Si lo que quires es crear un archivo. Puedes utilizar estos dos mayor que. Prueba con el siguiente código.

```

cd lecc-02
echo "El texto de mi archivo" >> archivo.txt

```

El doble mayor qué desvía lo que sería el resultado de `echo` a la terminal (o el de cualquier otro comando) hacia el archivo. Además de que, cuando ya hay contenido en el archivo, pone el nuevo contenido debajo de este.

```

echo "Segundo texto de mi archivo" >> archivo.txt

```

## cat

Una de las formas más utilizadas para ver el contenido de un archivo es `cat`. Este comando recibe como argumento un archivo e imprime a la consola el contenido de éste.

```

cat "archivo.txt"
// El texto de mi archivo
// Segundo texto de mi archivo

```

## \>

Si sólo utilizas un mayor qué se eliminará el contenido de tu archivo, poniendo en él sólo el nuevo contenido.

```

echo "Tercer texto" > archivo.txt
cat "archivo.txt"
// Tercer texto

```

Eso es todo por esta lección, sigan  programando.
