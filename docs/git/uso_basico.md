---
tags:
 - Git
#  - GitHub
 - Bash
---


# Uso básico


## Inicialización - `init`

Este comando crea un repositorio Git en la ubicación actual:
```bash
 git init
```
creando automáticamente la subcarpeta oculta `.git` con toda la información del repositorio, sus cambios, etc. 
Esta carpeta es manejada exclusivamente por Git y **no se sube** al servidor remoto.

<!-- 
!!! danger "Sobreescritura de repositorios"

    Si el repositorio ya fue creado el llamar de nuevo al comando `init` lo sobreescribirá, borrando toda la informacioón previa.
    Prestar atención antes de usarlo.
 -->


## Agregado - `add`



El comando `add` añade al repositorio los cambios realizados hasta el momento del archivo especificado únicamente.

```bash title="Agregado - archivo único"
git add nombre_archivo
```

Añade al repositorio la carpeta indicada completa:

```bash title="Agregado - carpeta completa"
git add nombre_directorio
```

Añade al repositorio las modificaciones de todos los archivos indicados:

```bash title="Agregado - múltiples archivos"
git add  nombre_archivo_1  nombre_archivo_2  nombre_archivo_3
```

Añade al repositorio todos los archivos terminados en la extension indicada:
```bash title="Agregado - archivos por extension"
git add  *.extension_archivo
```
Ejemplo: sólo archivos TXT
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

El comando `status` da un resumen del proyecto,
incluyendo la rama utilizada actualmente por Git,
las actualizaciones realizadas del proyecto y archivos incluidos, 
distinguiendo:

- archivos ya guardados;
- archivos con cambios pendientes de guardado;
- archivos no incluidos.

Uso:

```bash title="Estado"
git status
```

Con la opción `-s` se muestra solamente los archivos del proyecto indicando cuales están alterados y guardados y cuáles no:
```bash title="Estado (resumido)"
git status -s
```


## Compromiso - `commit`

Compromete (guarda) los cambios realizados al proyecto:

```bash title="Compromiso"
git commit -m “breve_descripción”
```

Este comando crea una especie de punto de guardado
con una descripción y un número identificador,
al cual se puede volver posteriormente.

El compromiso siempre va precedido por el comando `add`, 
el cual debe ser usado al menos una vez para registrar algún cambio en el proyecto:

```bash title="Compromiso - un archivo"
git add archivo_modificado
git commit -m “breve_descripción”
```


Una alternativa resumida 
para comprometer cambios de un único archivo
es usar directamente las opciones combinada `am`:

```bash title="Compromiso - único archivo del proyecto"
git commmit -am “breve_descripción”
```

la cual presupone que el archivo ya había sido añadido al proyecto previamente.


## Mover y renombrar archivos


Si un archivo es renombrado o movido de lugar
de manera directa
entoces Git interpreta que ese archivo fue eliminado 
y que otro archivo distinto fue creado,
haciendo que el guardado de cambios sea más ineficiente debido a la potencial redundancia de datos dentro del repositorio.

Por este motivo es más eficiente usar el comando `mv` como opción de git:


<div class="grid cards" markdown>

```bash title="Renombrar archivo"
git mv nombre_archivo nuevo_nombre
```

```bash title="Mover archivo"
git mv nombre_archivo ruta_destino/
```
</div>

De esta forma Git registra que el cambio producido en el proyecto es un simple movimiento de archivo 
y puede recrearlo o deshacerlo con una simple oeración. 
Además el cambio ya queda agregado al proyecto (*added*).



## Eliminar archivos

El comando `rm` también puede ser combinado con `git`:

```bash title="Eliminar archivo"
git rm nombre_archivo
```
de esta forma la operación ya queda agregada en el repositorio.


## Observar cambios 

El comando `diff` indica qué cambios fueron realizados en cada archivo alterado respecto de su último estado agregado (*added*) o comprometido (*commited*): 
```bash title="Diferencias - no agregadas"
git diff
```
Sólo se muestran cambios pendientes de agregar en el repositorio. 
Si se busca ver qué cambios ya fueron agregados al repositorio entonces se agrega la opción `staged`:

```bash title="Diferencias - ya agregadas"
git diff --staged
```

Para ver solamente los cambios en un archivo específico ya *trackeado* se indica su nombre:

```bash title="Diferencias - por archivo"
git diff nombre_archivo
```

!!! tip "Caracter de escape"
    Se sale del reporte por terminal con la tecla ++q++.

<!-- 

## HEAD

**HEAD** es un apuntador de Git que indica cuál de todas las versiones comprometidas del repositorio es la que está mostrando actuamente.

Este apuntador es muy importante cuando se necesita restablecer el código a commits antiguos, es decir a versiones viejas.
 -->


## Restauración 


Una forma de restaurar el archivo a su último estado, sea éste un *add* o un *commit*, es mediante el comando `restore`:

```bash
git restore nombre_archivo
```

Si se necesita anular el último agregado de archivo se agrega la opción `staged`.
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

El comando `log` proporciona un historial de los *commits* realizados:


```bash title="log - completo"
git log
```

donde se muestra una lista en orden de los commit realizados con su número de identificador,
su descripción realizada, etc.
También se agrega información del autor de cada *commit*, su mail, fecha de guardado, etc.
Los cambios comprometidos más recientes aparecen primero. 

Una variante resumida se obtiene agregando la opción `--oneline`:

```bash title="log - resumido"
git log --oneline
```

donde se omite la información del autor y
el resultado es algo como esto:

``` bash
4536537 (HEAD -> master, origin/master) Proyecto reorganizado 3
c0579b8 Proyecto reorganizado 2
1bdac61 Proyecto reorganizado
... (commits previos)
```


De esta pantalla informativa se sale con la tecla ++q++.

Aparecen indicados varios elementos adicionales:

- El apuntador `HEAD` que indica qué *commit*  (qué "versión") del proyecto es el que Git muestra actualmente; 
- información de la ramificación actual del repositorio;
- información de la version remota del repositorio.

Estos elementos serán explicados más adelante.


<!-- 
## HEAD

**HEAD** es un apuntador de Git que indica cuál de todas las versiones comprometidas del repositorio es la que está mostrando actuamente.

Este apuntador es muy importante cuando se necesita restablecer el código a commits antiguos, es decir a versiones viejas.
 -->
