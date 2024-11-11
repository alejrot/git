---
tags:
 - git
#  - github
---


# Forks en GitHub



## actualizar fork local
https://styde.net/actualizar-el-fork-de-un-repositorio-de-github/

```bash
# Agregar la referencia al repositorio remoto original, al cual llamaremos «upstream», esto lo logramos con:
git remote add upstream https://github.com/whoever/whatever.git
# Traernos todas las ramas de dicho repositorio remoto con:
git fetch upstream
# Irnos a la rama que queremos actualizar, por ejemplo master: 
git checkout master
# Reescribir nuestra rama master con los commits nuevos de la rama master del repositorio original con:
git rebase upstream/master
# Finalmente si queremos actualizar nuestro fork remoto, lo haremos ejecutando 
git push -f origin master
```



## actualizar fork desde pagina de github
https://victorhckinthefreeworld.com/2021/01/21/actualizar-un-fork-de-un-repositorio-git-desde-la-interfaz-web-de-github/










https://docs.github.com/es/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork?platform=windows


https://victorhckinthefreeworld.com/2021/01/21/actualizar-un-fork-de-un-repositorio-git-desde-la-interfaz-web-de-github/



## Sincronizar
https://www.freecodecamp.org/espanol/news/como-sincronizar-tu-fork-con-el-repositorio-original-de-git/


### Configurar

```bash
# Agregar un nuevo repositorio upstream remoto
git remote add upstream https://github.com/PROPIETARIO_ORIGINAL/REPOSITORIO_ORIGINAL.git

# Sincroniza tu Fork
git fetch upstream
git checkout master
git merge upstream/master
```


```bash
# solo indicará 'origin' (nuestro fork)
git remote -v
```

```bash
# agregar 'upstream' (fuente original) 
git remote add upstream https://github.com/PROPIETARIO_ORIGINAL/REPOSITORIO_ORIGINAL.git
```



```bash
# ahora indicará 'origin' y 'upstream'
git remote -v
```

### Actualizar


```bash
# ir a rama principal
git checkout master
# Switched to branch 'master'
```

```bash
# detectar cambios
git fetch upstream
```



```bash
# traer cambios
git merge upstream/master
```



## Pull Requests en GitHub

https://docs.github.com/es/pull-requests

https://www.freecodecamp.org/espanol/news/como-crear-tu-primer-pull-request-en-github/


