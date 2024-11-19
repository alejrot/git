---
tags:
 - Git
 - GitHub
#  - Bash
---

## Alias de comandos Git

Se pueden **crear alias** para los comandos más usados
```bash
git cofig --global alias.apodo   comandos
```

A continuación se proponen algunos ejemplos de alias útiles.


!!! tip "**Comando *unstage***"

    Crea un comando `unstage` para descartar cambios de archivo
    ```bash
    git config --global alias.unstage 'reset  HEAD --'
    ```
    Ahora estas dos instrucciones son equivalentes:
    ```bash
    git unstage <archivo>
    git reset HEAD <archivo>
    ```

!!! tip "**Comando *tree***"

    Crea un comando'tree' para visualizar los commits, tags y ubicacion del HEAD de forma resumida:
    ```bash
    # Recomendado: crear comando 'tree'
    git config --global alias.tree "log --graph --decorate --all --oneline" 
    ```