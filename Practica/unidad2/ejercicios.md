# Git Remoto

## Ejercicio1
> Crear un nuevo repositorio público y vacío en GitHub con el nombre libro-git.  
> Añadirlo al repositorio local del libro (creado en el Trabajo Prácco 1).  
> Mostrar todos los repositorios remotos configurados.  

~~~ git
[me posiciono en el repositorio local]
git remote add origin https://github.com/pala83/TIO-resumen.git
git branch -M main
~~~

## Ejercicio2
> Una vez configurado el repositorio remoto  
> 1. ¿aparecen los cambios en GitHub? ¿Por qué? Publicar/Subir los cambios del repositorio local al repositorio remoto de GitHub.  
> 2. ¿Qué comando se debe ulizar en este caso para poder publicar/subir dichos cambios? ¿Por qué?  
> 3. Acceder a GitHub y comprobar que se han subido los cambios mostrando el historial de versiones.  

1. Los cambios no aparecen en Github, porque yo ne he **pusheado** los cambios de mi repositorio *local* a la direccion de repositorio *remoto* que asigne en el Ejercicio1.
~~~ git
git push -u origin main
~~~

2. El comando que se debe utilizar para subir los cambios al repositorio remoto es:
~~~ git
git push -u origin main
~~~
Se necesita este comando, porque el **-u** establece una relacion de seguimiento entre el repositorio local y el repositorio remoto, esta relacion se establece una unica vez, ya que se pueden tener varios repositorios remotos en un repositorio local.  
**main** es el nombre que le puse a la rama principal de mi repositorio local, y **origin** es el nombre asignado al repositorio remoto

## Ejercicio3
> Colaborar en el repositorio remoto libro-git de otro usuario.  
> Clonar su repositorio libro-git.  
> Añadir el archivo autores.txt que contenga su nombre de usuario y su correo electrónico.  
> Añadir los cambios a la zona de intercambio temporal (área de preparación).  
> Confirmar los cambios con el mensaje “Añadido autor”.  
> Subir los cambios al repositorio remoto.  
> Entre los diferentes colaboradores generar conflictos en múlples archivos y resolverlos. Analizar el  
> registro de confirmaciones con git log.  

- [Pedirle a un coleguita que me agregue de colaborador en su repositorio]  
    - Alternativa [Pull request]
- [posicionarme en un directorio fuera de mi repositorio]
~~~ git
git clone https://github.com/fulanito/TIO-resumen.git
cd TIO-resumen
echo "Autor: Ulises Palazzo" >> autores.txt
echo "Email: ulipalazzoo@gmail.com" >> autores.txt
echo "----------------------------" >> autores.txt
git add autores.txt
git commit -m "Añadido autor"
git push
    [posiblemente resolver conflictos]
git log --oneline --graph
~~~