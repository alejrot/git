---
tags:
 - Git
#  - GitHub
#  - Bash
---


# Introducción

Git funciona monitoreando los archivos en la carpeta de cada repositorio.
Si se detectan cambios en la estructura de archivos o en el contenido de los mismos entonces Git los detecta y permite consolidar los cambios o deshacerlos.

## Etapas

Los repositorios de Git trabajan en cuatro grandes etapas:



## 0.Creación (*untracked*)

Se crea un nuevo repositorio vacío con el comando `init`.
En esta primera instancia del repositorio no hay seguimiento de archivos.


## 1.Cambios preliminares (*stage*)

Es una etapa intermedia dentro del computador donde el usuario decide qué archivos añadir (ó quitar) y donde se guardan los cambios preliminares realizados sobre los mismos.

Utiliza la instrucción `add` para registrar los cambios en los archivos de interés.

## 2.Confirmación de cambios (*commit*)

Etapa donde se actualizan (guardan) los cambios hechos en los archivos del repositorio y se incorpora la numeración y una descripción de las modificaciones realizadas. 

Utiliza la instrucción `commit` para crear puntos de guardado del repositorio también llamados *commit*.

## 3. Sincronización con servidor remoto

<!-- 
Destino final de los archivos cuando se trabaja en equipo y/o el repositorio es público. 
 -->

Los repositorios están preparados para ser sincronizados con servidores remotos, 
con el fin de trabajar en equipos, compartir los proyectos al público, hacer copias de respaldo, etc.

La sincronización usa la instrucción `push` ("empujar") para subir los cambios del repositorio local al servidor 
y usa `pull` ("tirar") para actualizar los repositorios locales.

