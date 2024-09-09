# Sección I. Creación y actualización de repositorios

## Ejercicio1
> Configurar Git definiendo el nombre del usuario, el correo electrónico y activar el coloreado de la salida. Mostrar la configuración final.

~~~ git
git config --global user.name "Ulises"
git config --global user.email "ulipalazzoo@gmail.com"
git config --global --list"
~~~
comandos opcionales
~~~ git
git config --global color.ui auto
git config --global init.defaultbranch main
~~~

## Ejercicio2
> Crear un repositorio nuevo con el nombre *libro* y mostrar su contenido.

~~~ git
mkdir libro
cd libro
git init
ls -la
~~~

## Ejercicio3

> Comprobar el estado del repositorio.  
> Crear un archivo indice.txt con el siguiente contenido:  
> - Capítulo 1: Introducción a Git  
> - Capítulo 2: Flujo de trabajo básico  
> - Capítulo 3: Repositorios remotos  
>
> Comprobar de nuevo el estado del repositorio.  
> Añadir el archivo a la zona de intercambio temporal.  
> Volver a comprobar una vez más el estado del repositorio.  

~~~ git
git status
echo "Capítulo 1: Introducción a Git" >> indice.txt
echo "Capítulo 2: Flujo de trabajo básico" >> indice.txt
echo "Capítulo 3: Repositorios remotos" >> indice.txt
git status
git add indice.txt
git status
~~~

## Ejercicio4
> Realizar un commit de los últimos cambios con el mensaje “Añadido índice del libro.” y ver el estado del repositorio.

~~~ git
git commit -m "Añadido índice del libro."
git status
~~~

## Ejercicio5
> Cambiar el archivo indice.txt para que contenga lo siguiente:  
> - Capítulo 1: Introducción a Git  
> - Capítulo 2: Flujo de trabajo básico  
> - Capítulo 3: Gestión de ramas  
> - Capítulo 4: Repositorios remotos  
> 
> Mostrar los cambios con respecto a la última versión guardada en el repositorio.  
> Hacer un commit de los cambios con el mensaje “Añadido capítulo 3 sobre gestión de ramas”.  

~~~ git
echo "Capítulo 4: Repositorios remotos" >> indice.txt
git diff HEAD..HEAD~1
git add .
git commit -m "Añadido capítulo 3 sobre gestión de ramas"
~~~

# Sección II: Historial de cambios

## Ejercicio1
> Mostrar el historial de cambios del repositorio.  
> Crear la carpeta *capítulos* y crear dentro de ella el archivo *capitulo1.txt* con el siguiente texto.  
> - **Git es un sistema de control de versiones ideado por Linus Torvalds.**  
> 
> Añadir los cambios a la zona de intercambio temporal.  
> Hacer un commit de los cambios con el mensaje “Añadido capítulo 1.”  
> Volver a mostrar el historial de cambios del repositorio.  

~~~ git
git log
mkdir capítulos
cd capítulos
echo "Git es un sistema de control de versiones ideado por Linus Torvalds." >> capitulo1.txt
git add .
git commit -m "Añadido capítulo 1."
git log
~~~

# Ejercicio2
> Crear el archivo *capitulo2.txt* en la carpeta capítulos con el siguiente texto.  
>> El flujo de trabajo básico con Git consiste en: 1- Hacer cambios en  
>> el repositorio. 2- Añadir los cambios a la zona de intercambio  
>> temporal. 3- Hacer un commit de los cambios.  
>
> Añadir los cambios a la zona de intercambio temporal.  
> Hacer un commit de los cambios con el mensaje “Añadido capítulo 2.”  
> Mostrar las diferencias entre la última versión y dos versiones anteriores.  

~~~ git
echo "El flujo de trabajo básico con Git consiste en: 1- Hacer cambios en el repositorio. 2- Añadir los cambios a la zona de intercambio temporal. 3- Hacer un commit de los cambios." >> capitulo2.txt
git add .
git commit -m "Añadido capítulo 2."
git diff HEAD..HEAD~2
~~~

## Ejercicio3
> Crear el archivo *capítulo 3.txt* en la carpeta capítulos con el siguiente texto.  
>> Git permite la creación de ramas lo que permite tener distintas versiones  
>> del mismo proyecto y trabajar de manera simultánea en ellas.  
> 
> Añadir los cambios a la zona de intercambio temporal.  
> Hacer un commit de los cambios con el mensaje “Añadido capítulo 3.”  
> Mostrar las diferencias entre la primera y la última versión del repositorio.  

~~~ git
echo "Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultánea en ellas." >> capítulo 3.txt
git add .
git commit -m “Añadido capítulo 3.”
git log --oneline
    [copio el HASH de la primera version]
git diff [pego HASH]..HEAD
~~~