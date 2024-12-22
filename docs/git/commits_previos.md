---
tags:
 - Git
#  - GitHub
#  - Bash
---

# Commits previos


<!-- # Volver a los commit previos  (tiene varios errores ) -->
El comando 'reset' nos permite cambiar de versión, con tres modalidades: hard, mixed y soft
HEAD indica el commit usado en el presente (versión actual del proyecto).
'hard' es una de las variantes del reset, que actualiza todo el proyecto a la versión requerida.


Siempre podremos volver al ultimo guardado con el comando ***reset***:
```bash
git reset   # regreso al último commit realizado
```

**IMPORTANTE:** Hay que guardar los últimos cambios antes para que no se pierdan. Y si los commits a omitir ya están compartidos en un repositorio público pueden producirse errores. Cuidado.
```bash
git reset --hard HEAD~1
```
Retrocedemos al commit inmediatamente anterior.Oculta el commit actual.

!!! tip "HINT"
    
    El carácter `~` se obtiene escribiendo ++altgr+4++

```bash
git reset --hard HEAD~<n>
```
Retrocedemos n posiciones de guardado, ocultando las posiciones posteriores.


<!-- ```bash
git reset --hard HEAD <clave_commit>
``` -->
<!-- 
Nos movemos al commit identificado por la clave. Puede ser un guardado posterior al HEAD actual.  
-->

Oculta los commits posteriores al elegido como destino.



## Navegación por índices

El comando `reflog` muestra el historial de *commits* del repositorio y lo combina con el historial de movimientos. 
Además, a cada estado le asigna un índice auxiliar que ayuda a navegar entre commits,
donde el índice `0` corresponde al estado más reciente.

Repasa el historial de guardados y movimientos:

```bash
git reflog
```
El comando no requiere argumentos adicionales.

Para poder "navegar" entre estados en base a los índices de `reflog` 
se usa el comando `reset` con la opción `HEAD@`:


```bash
git reset --hard HEAD@{numero_indice}
```

Esto nos mueve al guardado indicado por el número de índice.


!!! warning "cambio de índices"

    Cada vez que se llama al comando `reset` cambian los índices dados por `reflog`
    


## Buscar commmit por id

El comando `checkout`permite
saltar a un guardado particular en base a su identificador:

```bash
git checkout id_commit
```

<!-- 
Seleccionar el actual punto de guardado como `head`:
```bash
git checkout HEAD
``` -->
