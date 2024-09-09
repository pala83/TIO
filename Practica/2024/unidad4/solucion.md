# Trabajo practico 4
## Ejercicio 1

> - Eliminar la última línea del archivo indice.txt y guardarlo.
> - Comprobar el estado del repositorio.
> - Deshacer los cambios realizados en el archivo indice.txt para volver a la versión anterior del archivo.
> - Volver a comprobar el estado del repositorio.

~~~ git
[Modifico la ultima linea del archivo]
- git status
- git checkout -- indice.txt
- git status
~~~

## Ejercicio 2

> - Eliminar la última línea del archivo indice.txt y guardarlo.
> - Añadir los cambios a la zona de intercambio temporal.
> - Comprobar de nuevo el estado del repositorio.
> - Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.
> - Comprobar de nuevo el estado del repositorio.
> - Deshacer los cambios realizados en el archivo indice.txt para volver a la versión anterior del archivo.
> - Volver a comprobar el estado del repositorio.

~~~ git
[Elimino la ultima linea del archivo indice.txt]
- git add .
- git status
- git reset indice.txt
- git status
- git checkout -- indice.txt
- git status
~~~

## Ejercicio 3

> - Eliminar la última línea del archivo indice.txt y guardarlo.
> - Eliminar el archivo capitulos/capitulo3.txt.
> - Añadir un archivo nuevo capitulos/capitulo4.txt vacío.
> - Añadir los cambios a la zona de intercambio temporal.
> - Comprobar de nuevo el estado del repositorio.
> - Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.
> - Comprobar de nuevo el estado del repositorio.
> - Deshacer los cambios realizados para volver a la versión del repositorio.
> - Volver a comprobar el estado del repositorio.

~~~ git
[Elimino la ultima linea del archivo indice.txt]
- No tengo el archivo, lo creo y lo confirmo [comandos innecesarios]
  - echo "Una porcion de texto para poder simular que el archivo tiene algo :D" >> capitulos/capitulo3.txt
  - git commit -am "agrego el capitulo 3"
- rm capitulos/capitulo3.txt
- touch capitulos/capitulo4.txt
- git add .
- git status
- git reset .
  - Esto es una version reducida de [git reset --mixed HEAD .] ya que por defecto reset utiliza el parametro "mixed" en HEAD
- git status
- git checkout -- .
  - El archivo en blanco no se borra, porque es un archivo en blanco y no se porque  hace lio, se puede borrar con git asi.
  - git clean -f
- git status
~~~

## Ejercicio 4

> - Eliminar la última línea del archivo indice.txt y guardarlo.
> - Eliminar el archivo capitulos/capitulo3.txt.
> - Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Borrado accidental.”
> - Comprobar el historial del repositorio.
> - Deshacer el último commit pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal.
> - Comprobar el historial y el estado del repositorio.
> - Volver a hacer el commit con el mismo mensaje de antes.
> - Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.
> - Comprobar de nuevo el historial y el estado del repositorio.

~~~ git
[Elimino la ultima linea del archivo indice.txt]
- rm capitulos/capitulo3.txt
- git commit -am "borrado accidental"
- git log
- git reset HEAD~1
  - Resumen del comando [git reset --mixed HED~1]
- git log
- git commit -am "borrado accidental"
- git log
~~~
