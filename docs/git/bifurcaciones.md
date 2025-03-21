---
tags:
 - Git
#  - GitHub
#  - Bash
---

# Bifurcaciones

Git permite gestionar múltiples ramas o bifurcaciones (*branches*) en un mismo proyecto, lo cual permite amntener versiones alternativas de un mismo proyecto, implementar correcciones y mejoras en paralelo a la rama en producción, etc.


## Informacion de ramas - `branch`

Indicar qué ramas del proyecto  hay disponibles y en cuál nos encontramos:
```bash
git branch
```


!!! info "Rama principal"
    La rama creada al inicializarse el proyecto suele llamarse `master` o `main`, dependiendo de la versión de Git usada.



## Crear ramas


Para crear una nueva rama en el proyecto:

```bash
git branch nombre_nueva_rama
```

## Cambio de rama actual

Conmuta a la rama elegida del proyecto:

```bash
git switch nombre_rama
```

Renombrar una rama:
```bash
git branch -m nombre_rama nuevo_nombre_rama
```
Ejemplo:  de master a main   
```bash
git branch -m master main
```


!!! info "Estado y cambio entre ramas"
    Git requiere que **todos** los cambios hechos sobre los archivos del repositorio estén guardados o descartados antes de permitir el cambio de rama.

    Si hay cambios provisorios se puede recurrir al guardado provisional, con el [comando `stash`](#guardado-provisorio---stash)


## Unión de Ramas - `merge`

Las versiones paralelas del proyecto pueden reunirse para recolectar los cambios realizados entre ellas.
```bash
git switch nombre_rama_definitiva
```
<!-- 
Es preferible el comando 'switch' porque es más respetuoso del contenido que 'checkout' 
-->
Nos ubicamos en la rama que queremos actualizar y mantener.
```bash
git merge rama_alterna
```
Elegimos la rama de la que se leerán los cambios a añadir. Esta última NO dejará de existir sino que seguirá igual.


## Eliminación de ramas

Las ramas locales que ya no sean necesarias se eliminan con la opción `-d`:

```bash title="Eliminar rama"
git branch -d  nombre_rama
```

!!! tip "Nombres de rama"
    Se puede eliminar y volver a crear una rama con el mismo nombre. 


