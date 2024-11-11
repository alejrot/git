---
tags:
 - git
 - github
---


# Taller Miududev - Git para aportar a proyectos

[Video](https://www.youtube.com/watch?v=niPExbK8lSw)


INFO: ***SCM: Source Code Management***


## Buscar proyectos para contribuir

[For Good First Issue](https://forgoodfirstissue.github.com)

Proyectos abiertos a contribuciones, con impacto en ONGs, gobiernos, etc.

[Good First Issue](https://goodfirstissue.dev)



## Tip: buscar archivos 'Contributing'

Es una buena idea buscar los requisitos para contribuciones de proyectos ya establecidos para conocer buenas practicas, ver requisitos, etc .





## Clonar proyectos


Tres opciones: 
- HTTP: no recomendada, pues se pide usuario y contraseña
- SSH: requiere clave SSH (configuracion previa dependiente del sistema opeerativo)
- GitHub CLI


Clonado (completo):

    git clone http:ruta_repo        # HTTP
    git clone git@ruta_repo         # SSH
    gh repo clone user/repo         # GitHub CLI


Clonado - sólo último commit (suele ahorrar MUCHO espacio en disco) - opcion `--depth=1`:

    git clone ruta_repo  --depth=1


### Modificar 



    git status
    git add archivo


Commit:
    
    git commit --message "mensaje del commmit"


MAL: el repositorio online NO es nuestro

    git push -u origin main



## Forks

El fork es la copia del proyecto original a propiedad del nuevo usuario.


El fork puede ser completo o puede abarcar una sola rama original.

Para trabajar se clona el repositorioi fork en vez de clonar el original.


    git remote --verbose


Info:
    origin --> nuestro repositorio
    upstream --> repositorio original


### Crear nueva rama

    git switch -c nombre_nueva_rama


TIP Hacer cambios en rama dedicada

    Es mejor EVITAR retocar la rama principal de nuestro fork para poder actualizarla fácilmente cuando el proyecto fuente haga cambios.



**INFO:  "git checkout" deprecated**
Los creadores de git ya NO recomiendan usar el comando checkout por ser multiuso, sirviendo tanto para cambiar de ramas como para restaurar ramas y archivos.
Comandos sustitutos: **switch** y **restore**



TIP: "ser quirúrgico"
Para proponer cambios al proyecto original es mejor hacer los mínimos cambios necesarios para cumplir el objetivo. Evitar la tentación de hacer cambios de estilo, renombrar archivos, etc.


TIP: evitar signos de puntuación en los commits
(Titulo: maximo:72 caracteres, recomendado 50 caracteres)
(descripcion: recomendado 72 caracteres)



TIP commits con titulo y descripción

    git commit -m "Title" -m "Description...."


    https://stackoverflow.com/questions/16122234/how-to-commit-a-change-with-both-message-and-description-from-the-command-li



INFO:  Commit: "Confirmar cambios"



## Pull request

En el pedido de cambios se indica tanto el origen (repositorio fork y rama de los cambios) y el destino (repositorio origen y rama, típicamente la principal).

En GitHub se pueden adjuntar capturas de pantallas , videos, etc. Sin embargo es conveniente hacer las pull requests lo más concisas y explicativas que sea posible

Dos opciones: "Draft pull request" (pedido borrador, no se puede aceptar hasta completar cambios) y "Create puyll request" (pedido definitivo).



## GitHub Flow


Los pasos previos siguen la guía del GitHub Flow: una rama de desarrollo que implementa pocos cambios y se une a la rama principal del proyecto.

Las ramas ya "mergeadas" por los administradores del proyecto pueden eliminarse. Para recuperar el trabajo hecho o simplemente traer nuevos cambios de terceros al fork hay que **sincronizar**. Para hacerlo desde consola:

    git pull upstream main      # descarga de cambios desde proyecto original (a local)
    git push origin main        # subida a nuestro repositorio (remoto)



Traer ramas desde repositorio remoto

    git fetch




## Agregar repositorio remoto


Un mismo repositorio puede apuntar a múltiples repositorios remotos


    git remote add alias_remoto ruta_remoto




