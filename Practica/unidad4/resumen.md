# Deshacer cambios

## Indice
- [git commit --amend](#git-commit---amend)
- [git checkout --[archivo]]()
- [git reset](#git-reset)
- [git revert](#git-revert)
- [git stash](#git-stash)

# git commit --amend
## USO:
- Permite modificar el ultimo commit realizado
- Se utliza para agregar modificaciones a un commit anteriormente realziado y cambiar el mensaje de confirmacion.

## Ejemplo de uso:
~~~
- git add .
- git commit -m "Cambios en main.js"
- git status
- [hago cambios]
- git add .
- git commit --amend -m "Cambios realizados en main.js y service.js"
- git log
~~~
# git checkout --[archivo]
## USO:
- Permite revertir archivos individuales o repositorios enteros
- Se utiliza cuando queremos deshacer un cambio realizado sobre un archivo determinado que ya agregamos al working direcory con git add .

# Ejemplo de uso:
~~~
- git status //hay cambios realizados en el archivo js/services.js
- git checkout -- js/service.js
- git status //ya no hay cambios
~~~

# git reset
## USO:
- Permite volver a versiones anteriores y limpiar el repositorio
- Se utiliza cuando queremos deshacer un archivo preparado (git add) o para deshacer commits (git commit).
- Tiene un monton de parametros:
    - **git reset --hard**: deshacer todos los cambios en archivos modificados y preparados.
    - **git reset HEAD [archivo]**: deshacer el archivo preparado.
    - **git reset HEAD~[n]**: deshacer los **n** commits manteniendo las modificaciones.
    - **git reset [HASH]**: se deshacen los commits posteriores al commit especificado.
- **IMP**: git reset solo no existe.

### Detalle de los commits SOFT VS HARD.
- **git reset --soft**: los cambios producidos pro los commits siguen permaneciendo en el repo local
- **git reset --hard**: se pierden todas las modificaciones realizadas por lso commits eleminados.

## Ejemplo de uso:
~~~
- git pull
- [modifico un archivo (o muchos)]
- [tu amigo te dice que ya resolvio todo y ya lo subio al repo remoto]
- git reset --hard
- git pull
~~~

# git revert
## USO:
- Permite revertir el estado del proyecto, generando un nuevo commit que revierte los cambios realizados.
- Los cambios no son eliminados del historial de cambios, conservando dicha informacon.
- **IMP**: Es mas seguro que un reset.

## Ejemplo de uso:
~~~
- git push
- [hago modificaciones]
- git add .
- git commit -m "version 1.1"
- git push
- [hago modificaciones]
- git add .
- git commit -m "version 1.2"
- git push
- [hago modificaciones]
- git add .
- git commit -m "version 1.3"
- git push
- git revert HEAD~3
    - [nvim: "esta todo mal vuelvo a la version 1"]
~~~

# git stash
## USO:
- Permite descartar los cambios, pero guardar provisionalmente los archivos modificados.
- Se utiiza cuando se requiere resolver un bug o desarrollar una nueva funcionalidad pero sin realizar el commit del trabajo realizado hasta el momento.
- Estos cambios se descartan, pero se guardan para continuar trabajando mas adelante.

### Parametros
- **git stash pop**: Los cambios guardados en el stash vuelven al working directory.
- **git stash list**: Se muestra el contenido de la pila de stash.
- **git stash apply <STASH>**: se aplica sobre el working directory los cambios del stash especificado.
- **git stash drop <STASH>**: elimina de la lista el stash especificado.

## Ejemplo de uso:
~~~
- 
~~~