---
tags:
 - Git
#  - GitHub
#  - Bash
---

# Guardado provisorio - `stash`

Git no permite el cambio de rama si los archivos tienen modificaciones no registradas.

El comando `stash` permite hacer guardados temporales 
para poder pasar a trabajar en otras ramas del proyecto 
sin recurrir a guardados definitivos adicionales con código defectuoso o incompleto.

Guardado temporal:
```bash
git stash 
```

Para recuperar los cambios provisorios (stash previos):
```bash
git stash pop
```
Listado de guardados temporales en la rama actual:
```bash
git stash list
```
Para ver los 'stash' en todo el proyecto:
```bash
git status --show-stash
```
Descarte de cambios provisorios:
```bash
git stash clear
```