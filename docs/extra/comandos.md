---
tags:
 - Git
#  - GitHub
 - Bash
---


# Comandos de Bash


Para manejar git es conveniente manejar algunos comandos básicos de la terminal.

La terminal más popular es Bash, cuyo comandos más básicos se enumeran a continuación.

## Explorar

Los archivos del actual directorio (carpeta) se consultan con el comando `ls`:


<div class="grid cards" markdown>
```bash title="Listar archivos - sólo visibles"
ls
```

```bash title="Listar archivos - todos"
ls -a
```
</div>

## Navegar

Consultar directorio actual 
```bash
pwd
```
Entrar a un sub directorio:
```bash
cd nombre_carpeta
```
!!! tip "HINT: autocompletado de nombres" 
    Escribir el nombre de archivos y carpetas parcialmente y entonces presionar TAB para autocompletar.

Retroceder al directorio superior:
```bash
cd ..
```

Entrar a una carpeta específica existente:
```bash
cd ‘ruta_de_carpeta’
```

## Manejo de directorios

Las carpetas se gestionan con los comandos `mkdir` y `rmdir`:

<div class="grid cards" markdown>

```bash title="Crear directorio"
mkdir nombre_carpeta
```

```bash title="Borrar directorio - sólo vacíos"
rmdir nombre_carpeta
```

</div>

## Mover y renombrar


Tanto los archivos como las carpetas se reubican con el nombre `mv`:

<div class="grid cards" markdown>


```bash title="Mover archivo"
mv  nombre_archivo  nombre_carpeta/
```

```bash title="Renombrar archivo"
mv  nombre_archivo  nuevo_nombre_archivo
```
</div>


## Manejo de archivos



Los archivos de texto se leen desde terminal con el comando `cat`:

```bash title="Leer archivo"
cat nombre_archivo
```

en tanto que pueden ser editados desde terminal con editores básicos como `nano` o `vim`:

<div class="grid cards" markdown>

```bash title="Editar archivo - nano"
nano nombre_archivo
```

```bash title="Editar archivo - vim"
vim nombre_archivo
```
</div>



Con `touch` se crea desde terminal un archivo vacío con el nombre indicado:


```bash title="Crear archivo vacio"
touch nombre_archivo
```

en tanto que para eliminarlo se usa `rm`:

```bash title="Eliminar archivo"
rm nombre_archivo
```

`rm` también permite eliminar carpetas con contenido interno:

```bash title="Eliminar directorio"
rm -r nombre_carpeta
```

## Editores de código

Los IDE's también pueden ser llamados desde la *shell* para leer y editar archivos:

```bash title="IDE - Editar archivo"
nombre_editor  nombre_archivo
```

aunque esta es una opción muy incómoda debido a que los IDE's habitualmente tienen una apertura lenta.

Ejemplos: 

=== "VSCode"

    ```bash title="VSCode - Editar archivo"
    code   nombre_archivo
    ```

=== "VSCodium"

    ```bash title="VSCodium - Editar archivo"
    codium nombre_archivo
    ```


!!! tip "TIP: abrir directorio como workspace"


    Se puede abrir el programa de edición elegido en el directorio actual 
    desde la terminal:

    ```bash title="IDE - Cargar directorio"
    nombre_editor  nombre_archivo
    ```
    Por ejemplo, para abrir VSCodium desde terminal
    con el directorio del proyecto actual precargado como *workspace*:

    === "VSCode"

        ```bash title="VSCode   - Cargar workspace"
        code   .
        ```

    === "VSCodium"

        ```bash title="VSCodium - Cargar workspace"
        codium .
        ```