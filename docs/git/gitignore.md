---
tags:
 - Git
#  - GitHub
 - Bash
---

# Archivo de excepciones 


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

    Extensión de archivo habitual para variables entorno: `.env`

    Simplemente agregar al `.gitignore`:

    ```
    *.env
    ```
