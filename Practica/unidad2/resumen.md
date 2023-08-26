# Versionado de Software Git Remoto

## Comandos

- **Ver repositorios remotos configurados**
    - git remote
- **Añadir repositorio remoto**
    - git remote add [nombre] [url]
- **Remover repositorio remoto**
    - git remote rm [nombre]
- **Ver ramas existentes en el repositorio**
    - git branch
        - git branch -u origin/main
        - git branch --set-upsteam-to=origin/main
- **Subir confirmaciones a repositorio remoto**
    - git push [nombre-remoto] [rama]
        - git push -u origin main
        - git push --set-upsteam origin main
- **Actualizar de repositorio remoto**
    - git pull [nombre-remoto] [rama]

## Pequeño resumen teorico
- **Github**: servidor de git mas conocido donde se almacenan repositorios de forma remota
- **Colaboradores**: integrantes de un equipo de desarrollo que pueden participar modificando nuestro repositorio remoto
- **Branch**: una ramificacion de un repositorio que sirve a forma de copia modificable, sirve para poder modificar el repositorio manteniendo una version original intacta.
- **Resolucion de conflictos**: entrelazar un *Branch* con su copia original, o con otro branch resolviendo las diferencias entre estos.