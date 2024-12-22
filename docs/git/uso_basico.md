---
tags:
 - Git
#  - GitHub
 - Bash
---


# Uso básico


## Inicialización - `init`

Crea un repositorio GIT en la ubicación actual (archivos y carpetas ocultos):
```bash
 git init
```
La subcarpeta oculta `.git` es manejada exclusivamente por Git y **no se sube** al servidor remoto.



!!! tip "TIP: abrir directorio como workspace"


    Se puede abrir el programa de edición elegido en el directorio actual 
    desde la terminal:

    ```bash
    nombre_editor .
    ```
    Por ejemplo, para abrir VSCodium desde terminal
    con el directorio del proyecto actual precargado como *workspace*:

    ```bash
    cd ruta_proyecto
    “codium .”  
    ``` 



## Agregado - `add`



Añade al repositorio los cambios realizados hasta el momento del archivo especificado únicamente.
```bash
git add nombre_archivo
```
Añade al repositorio la carpeta indicada completa:
```bash
git add nombre_directorio
```
Añade al repositorio las modificaciones de todos los archivos indicados:
```bash
git add  nombre_archivo_1  nombre_archivo_2  nombre_archivo_3
```

Añade al repositorio todos los archivos terminados en la extension indicada:
```bash
git add  *.extension_archivo
```
Ejemplo:
```bash
git add *.txt
```
!!! warning "Añadido de todos los archivos "

    Es una mala práctica porque puede añadir al proyecto archivos ajenos al programa: binarios, imágenes de entrada, archivos de salida del programa, etc.

    Algunas opciones para añadir todos los archivos existentes:

    ```bash
    git add .
    git add -A
    ```

## Estado del proyecto - `status`

El comando `status` da un resumen del proyecto:
```bash
git status
```
incluyendo la rama utilizada actualmente por Git;
las actualizaciones realizadas del proyecto y archivos incluidos, 
distinguiendo los ya guardados 
y los que tienen cambios pendientes de guardado.


Con la opción `-s` se muestra solamente los archivos del proyecto indicando cuales están alterados y guardados y cuáles no:
```bash
git status -s
```


## Compromiso - `commit`

Compromete (guarda) los cambios realizados al proyecto:
```bash
git commit -m “breve_descripción”
```
Este crea una especie de punto de guardado al cual se puede volver posteriormente con una descripción añadida por el usuario entre comillas. 
También asigna un número de clave identificadora para este punto de guardado.
Va precedido por el comando `add`:
```bash
git add nombre_archivo
git commit -m “breve_descripción”
```
Una alternativa resumida para trabajar con archivos previamente añadidos es usar directamente la opción `am`: 
```bash
git commmit -am “breve_descripción”
```

Elimina el archivo de proyecto indicado (puede revertirse)
```bash
git rm nombre_archivo
```


## Observar cambios 

El comando `diff` indica qué cambios fueron realizados en cada archivo alterado respecto de su último estado agregado (*added*) o comprometido (*commited*): 
```bash
git diff
```
Sólo se muestra cambios pendientes de guardar en el proyecto. 
Si se busca ver qué cambios ya fueron agregados al proyecto entonces se agrega la opción `staged`:

```bash
git diff --staged
```

Para ver solamente los cambios en un archivo específico ya trackeado se indica su nombre:

```bash
git diff nombre_archivo
```

!!! tip "Caracter de escape"
    Se sale del reporte por terminal con la tecla ++q++.



## Restauración 


Una forma de restaurar el archivo a su último estado, sea éste un *add* o un *commit*, es mediante el comando `restore`:

```bash
git restore nombre_archivo
```

Si se necesita deshacer el último agregado de archivo se agrega la opción `staged`.
```bash
git restore  --staged nombre_archivo
```

Una alternativa es usar el comando `reset HEAD`:

```bash
git reset HEAD nombre_archivo
```

el cual puede ser usado para anular el agregado de todos los archivos del proyecto:

```bash
git reset HEAD
```



## Información - `log`

Historial de los commits realizados:

```bash
git log
git log --oneline
```

muestra una lista en orden de los commit realizados, 
su número clave y su descripción realizada. 
Los cambios más recientes aparecen primero. 
Se sale con la tecla ++q++.



