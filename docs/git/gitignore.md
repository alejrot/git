---
tags:
 - Git
#  - GitHub
 - Bash
---

# Archivo de excepciones 


Puede crearse un archivo de excepciones llamado `.gitignore`, un archivo oculto donde se indican los archivos y rutas a ignorar por GIT.

## Creación

Es posible crear el archivo vacío desde la terminal:

```bash title="Archivo gitignore - Crear"
touch .gitignore
```

El archivo se puede editar con un editor de texto
donde se indica renglón a renglón cada archivo y directorio a ignorar por GIT. 

Formato:
``` title="Archivo gitignore - Excluir elementos"
nombre_archivo
nombre_carpeta/
nombre_carpeta/nombre_subcarpeta/
```
Se pueden indicar extensiones de archivo dentro del archivo de excepciones. Por ejemplo, para ignorar archivos de imagen del repositorio:

```git title="Archivo gitignore - excluir por extensión"
*.png
*.jpg
*.webp
```

Si todo salió bien el comando `status` dejará de avisar sobre los archivos y carpetas que deben ser ignorados.

## Agregado al repositorio

Se agrega al proyecto el archivo de excepciones:

```bash title="Archivo gitignore - Agregado"
git add .gitignore
```

De esta manera se previene el seguimiento accidental de archivos ajenos temporales, de archivos producidos por el programa del proyecto durante su uso, etc.

Si se requiere forzar el agregado de un archivo ya excluido se usa la opción `--force` ó `-f`:


!!! tip "Múltiples archivos de excepciones"
    Git permite usar múltiples archivos `.gitignore` dentro de un mismo proyecto,
    repartidos en distintos directorios. 
    Esto habilita usar distintos criterios de exclusión dentro de un mismo proyecto.


!!! danger "Variables de Entorno"

    Las variables de entorno (usuarios, contraseñas, bases de datos etc) NO deben agregarse al repositorio.
    Éstas suelen guardarse en archivos con extensión `.env`,
    por tal motivo es conveniente excluir esta extensión de los repositorios. 
    Para ello, simplemente agregar al `.gitignore`:

    ``` title="Excluir archivos de entorno"
    *.env
    ```
