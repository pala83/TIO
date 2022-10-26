# Ejercicio1
> Crear un nuevo branch bibliografía y mostrar los branches del repositorio

~~~
- git branch bibliografia
- git branch
~~~

# Ejercicio2

> Crear el archivo capitulos/capitulo4.txt y añadir el texto siguiente
> - En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.
> - Añadir los cambios a la zona de intercambio temporal.
> - Hacer un commit con el mensaje “Añadido capítulo 4.”
> - Mostrar la historia del repositorio incluyendo todos los branches.

~~~
- mkdir capitulos
- cd capitulos
- echo "En este capitulo veremos como usar GitHub para aloar repositorios en remoto." >> capitulo4.txt
- git add capitulo4.txt
- git commit -m "Añadido capitulo 4"
- git log
~~~

# Ejercicio3

> - Cambiar al branch bibliografía.
> - Crear el archivo bibliografia.txt y añadir la siguiente referencia
>   - Chac, S. and Straub, B. Pro Git. Apress.
> - Añadir los cambios a la zona de intercambio temporal.
> - Hacer un commit con el mensaje “Añadida primera referencia bibliográfica.”
> - Mostrar la historia del repositorio incluyendo todos los branches.

~~~
- git checkout bibliografia
- cd capitulos
- echo "Chac, S. and Straub, B. Pro Git. Apress." >> bibliografia.txt
- git add bibliografia.txt
- git commit -m "Añadida primera referencia bibliografica"
- git log
~~~

# Ejercicio4

> - Fusionar (mergear) el branch bibliografía con master.
> - Mostrar la historia del repositorio incluyendo todos los branches.
> - Eliminar el branch bibliografía.
> - Mostrar de nuevo la historia del repositorio incluyendo todos los branches.

~~~
- git checkout main
- git merge bibliografia
    - Proceso de merging
- git branch -d bibliografia
- git log
~~~

# Ejercicio5

> - Crear el branch bibliografía.
> - Cambiar a bibliografía.
> - Cambiar el archivo bibliografía.txt para que contenga las siguientes referencias:
>   - Scott Chac and Ben Straub. Pro Git. Apress.
> Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)
> - Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”
> - Cambiar a master.
> - Cambiar el archivo bibliografía.txt para que contenga las siguientes referencias:
>   - Chac, S. and Straub, B. Pro Git. Apress.
> Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
> - Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”
> - Fusionar el branch bibliografía con el branch master.
> - Resolver el conflicto dejando el archivo bibliografia.txt con las referencias:
> Chac, S. and Straub, B. Pro Git. Apress.
> Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
> Hodson, R. Ry’s Git Tutorial. Smashwords (2014)
> - Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Resuelto conflicto de bibliografía.”
> - Mostrar la historia del repositorio incluyendo todos los branches.

~~~
- git checkout -b bibliografia
- cd capitulos
- rm -f bibliografia.txt
- echo "Scott Chac and Ben Straub. Pro Git. Apress. Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)" >> bibliografia.txt
- git add bibliografia.txt
- git commit -m "Añadida nueva referencia bibliográfica."
- git checkout main
- rm -f bibliografia.txt
- echo "Chac, S. and Straub, B. Pro Git. Apress. Loeliger, J. and McCullough, M. Version control with Git. O’Reilly." >> bibliografia.txt
- git add bibliografia.txt
- git commit -m "Añadida nueva referencia bibliográfica."
- git merge bibliografia
    - Resolver conflictos
- git add .
- git commit -m "Resuelto conflicto de bibliografía."
- git log
~~~