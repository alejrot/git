---
tags:
 - Git
#  - GitHub
#  - Bash
---


# Comando `checkout`


El comando `checkout` sirve para manejar ramas y cambiar el `HEAD` de ubicación.
Este comando actualmente es evitado en favor de sus comandos sustitutos, 
los cuales son `branch`, 
`switch` 
y 





## Ramas


### Crear

Crear una nueva rama con el nombre indicado y pasa a la misma:
```bash
git checkout -b  nombre_nueva_rama
```
en este caso *git* nos pasa a la nueva rama automaticamente.


### Cambiar

Cambiar de rama
```bash
git checkout  nombre_rama
```

Es preferible el comando 'switch' porque es más respetuoso del contenido que 'checkout' 



## Restaurar Archivos 

Para deshacer los cambios hechos sobre un archivo preguardado con el comando `add`:
```bash
git checkout -- nombre_archivo  #deshace cambios no 'added'
```


