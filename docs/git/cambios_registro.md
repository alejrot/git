---
tags:
 - Git
#  - GitHub
 - Bash
---


# Cambios y registro


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

