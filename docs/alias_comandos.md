---
categories:
  - Search
  - Performance
readtime: 15
---
:fontawesome-solid-user-nurse:{.nurse}

:fontawesome-solid-computer-mouse:

:simple-github:

:simple-git:

:octicons-git-pull-request-draft-24:


|opcionm | signif|
|:---:|:---|
|:simple-github:{.nurse}| hola|
|:simple-git:{.nurse}|  chau|


## Alias de comandos Git

Se pueden **crear alias** para los comandos más usados
```bash
git cofig --global alias.<apodo> <comandos>
```
Ejemplo: crear un comando 'unstage' para descartar cambios de archivo


!!! tip "**Comando *unstage***"
    ```bash
    # Recomendado: crear comando'unstage'
    git config --global alias.unstage 'reset  HEAD --'
    ```
    Ahora estas dos instrucciones son equivalentes:
    ```bash
    git unstage <archivo>
    git reset HEAD <archivo>
    ```

!!! tip "**Comando *tree***"

     crear un comando'tree' para visualizar los commits, tags y ubicacion del HEAD de forma resumida:
    ```bash
    # Recomendado: crear comando 'tree'
    git config --global alias.tree "log --graph --decorate --all --oneline" 
    ```