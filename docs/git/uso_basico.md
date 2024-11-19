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
La subcarpeta oculta *.git* **no** se comparte a los otros desarrolladores.

Abre el programa de edicion elegido en el directorio actual:
```bash
EDITOR .
```
ej: abrir  VSCode en el directorio del proyecto
```bash
 “code .”  
```

## Agregado - `add`


Añade al repositorio los cambios realizados hasta el momento del archivo especificado únicamente.
```bash
git add <nombre_archivo>
```
Añade al repositorio la carpeta indicada completa:
```bash
git add <nombre_directorio>
```
Añade al repositorio las modificaciones de todos los archivos indicados:
```bash
git add <nombre_archivo1>  <nombre_archivo_2>  [...]
```

Añade al repositorio todos los archivos terminados en la extension indicada:
```bash
git add  *.<extension_archivo>
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

Resumen del proyecto: rama utilizada actualmente por GIT , actualizaciones realizadas del proyecto y archivos incluidos , distinguiendo los ya guardados y los que tienen cambios pendientes de guardado.

```bash
git status
```
Con la opción `-s` se muestra solamente los archivos del proyecto indicando cuales están alterados y guardados y cuáles no:
```bash
git status -s
```

## Observar cambios - `diff`

Indica qué cambios fueron realizados en cada archivo alterado: 
```bash
git diff
```
Este comando indica qué contenido se añadió y qué contenido se quitó. Sólo muestra cambios pendientes de guardar en el proyecto. 

Indica qué cambios fueron realizados en cada archivo alterado pero esta vez ya fueron agregados al proyecto y listos para comprometer:
```bash
git diff --staged
```
Para ver los cambios en un archivo específico ya trackeado:
```bash
git diff <archivo>
```

!!! tip "Caracter de escape"
    Se sale con la **tecla Q**.

## Compromiso - `commit`

Compromete (guarda) los cambios realizados al proyecto:
```bash
git commit -m “breve_descripción”
```
Este crea una especie de punto de guardado al cual se puede volver posteriormente con una descripción añadida por el usuario entre comillas. También asigna un número de clave identificadora para este punto de guardado. Va precedido por el comando *add*:
```bash
git add <archivo>
git commit -m “breve_descripción”
```
Una alternativa resumida para trabajar con archivos previamente añadidos es usar directamente la opción `-am`: 
```bash
git commmit -am “breve_descripción”
```

Elimina el archivo de proyecto indicado (puede revertirse)
```bash
git rm <nombre_archivo>
```

## Restauración - `restore`

Recupera el archivo de proyecto indicado (último estado).
```bash
git restore <nombre_archivo>
```
<!-- Recupera el archivo de proyecto indicado (última versión añadida al proyecto). -->

Deshacer el último agregado de archivo: opción `staged`.
```bash
git restore  --staged nombre_archivo
```


## Exclusión del proyecto

Hace que GIT deje de seguir los cambios del archivo indicado.
```bash
git reset HEAD nombre_archivo
```
Hace que GIT deje de seguir todos los archivos del directorio.
```bash
git reset HEAD
```



## Información - `log`

Historial de los commits realizados:
```bash
git log
git log --oneline
```
muestra una lista en orden de los commit realizados, su número clave y su descripción realizada. Los cambios más recientes aparecen primero. Se sale con la tecla ++q++.


<!-- 
## Archivo de excepciones - `.gitignore`


Puede crearse un archivo de excepciones llamado `.gitignore`, un archivo oculto donde se indican los archivos y rutas a ignorar por GIT.
```bash
touch .gitignore
```
Es posible crear el archivo desde la terminal. El archivo se puede editar con un editor de texto donde se indica renglón a renglón cada archivo y directorio a ignorar por GIT. Formato:
```
nombre_archivo
nombre_carpeta/
nombre_carpeta/nombre_subcarpeta/
```
Se pueden indicar extensiones de archivo dentro del archivo de excepciones. Por ejemplo, para ignorar archivos de imagen del repositorio:

```git 
*.png
*.jpg
*.webp
```


Se agrega al proyecto el archivo de excepciones:
```bash
git add .gitignore
```
Si todo salió bien el comando `status` dejará de avisar sobre los archivos y carpetas ignorados.

De esta manera se previene el seguimiento accidental de archivos ajenos temporales, de archivos producidos por el programa del proyecto durante su uso, etc.

Si se requiere forzar el agregado de un archivo excluido se usa la opción `--force` ó `-f`:


!!! tip "Múltiples archivos de excepciones"
    Git permite usar múltiples archivos .gitignore dentro de un mismo proyecto. Esto habilita usar distintos criterios de exclusión dentro de un mismo proyecto.


!!! danger "Variables de Entorno"

    Las variables de entorno (usuarios, contraseñas, bases de datos etc) NO deben agregarse al proyecto.

    Nombre de archivo habitual para variables entorno:  ***`.env`*** (archivo oculto)

    Simplemente agregar al `.gitignore`:

    ```
    .env
    ``` -->
