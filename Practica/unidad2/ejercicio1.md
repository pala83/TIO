# Ejercicio 1

> Crear un nuevo repositorio público y vacío en GitHub con el nombre libro-git.
> Añadirlo al repositorio local del libro (creado en el Trabajo Prác co 1).
> Mostrar todos los repositorios remotos configurados.

1. Ingreso a Git y creo el repositorio publico *libro-git*
2. utilizo la consola para posicionarme en el repos del libro
3. Comandos.
~~~
  - git init
  - git add README.md
  - git commit -m "first commit"
  - git branch -M main
  - git remote add origin [link del repo en git SSH o HTTP]
    - git remote set-url
  - git push -u origin main
~~~

puede ser que deba hacer un pull antes del git push por el readme.md
~~~
  - git pull origin main
~~~
si git se queja mucho por lo del pull tirar lo siguiente
~~~
  - git pull --rebase origin main
~~~
