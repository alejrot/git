---
tags:
 - Git
#  - GitHub
#  - Bash
---




# Repositorio Remoto

## Configurar repositorio remoto


Indicamos la dirección web del servidor y nuestro directorio que aloja el repositorio remoto del proyecto (se presupone que éste ya existe):
```bash
git remote add origin <URL/directorio/nombre_proyecto>
```

Ejemplo típico : repositorio en GitHub

    https://github.com/MI_USUARIO/MI_PROYECTO


Crea en el repositorio remoto la rama indicada y sube los cambios guardados realizados (*commits*) en el proyecto al servidor:
```bash
git push -u origin nombre_rama
```

!!! info "Rama principal"
    En el servidor  la rama `main` o `master` NO está creada por defecto, por lo que debe crearse:
    ```bash
    git push -u origin master
    ```
    <!-- git push --set-upstream origin master -->




## Actualizar repositorio remoto - `push`


El comando `pull` sube los nuevos *commits* del proyecto al servidor:

```bash
git push
```
Este comando sólo sube los guardados de la rama actual.




## Actualización de repositorio local - `pull` y `fetch`


El comando `pull` descarga las nuevas versiones desde el repositorio remoto al local:
```bash
git pull
```
A veces es necesario usarlo para  “unir” la rama remota con la actual del proyecto. 

Similar a `pull`  pero creando una rama alterna en nuestra estación de trabajoes el comando `fetch`:

```bash
git fetch
```



## Eliminar ramas


Eliminar la rama remota elegida:
```bash
git push remote  --delete <nombre_rama>
```
Elimina las ramas locales que ya no estén en el repositorio remoto:
```bash
git fetch -p 
```



## Como corregir errores de origen

Si aparece el error de subida porque “ el origen remoto ya existe” podemos escribir:


Permite saber a qué URL apunta el puntero origen (origin)
```bash
git remote -v
```



Elimina la URL ya cargada para poder empezar de nuevo:
```bash
git remote remove origin
```


Asigna una nueva dirección web para reemplazar la antigua.
```bash
git remote set-url origin <nueva_URL>
```

Cambia el nombre del puntero origin por uno distinto.
```bash
git remote rename origin <nuevo_puntero>
```






## Clonar repositorios 

El clonado hace una copia completa del proyecto indicado desde el repositorio y la guarda en el directorio actual. Usa el comando `clone`:

```bash
git clone <URL_del_proyecto>
```

Hay que instalar las dependencias, esto último depende del lenguaje de programación del proyecto. Cada lenguaje tiene sus propias prácticas y comandos. Recordar que el archivo `.gitignore` indica qué dependencias ignora GIT en el traspaso de los proyectos.

Si no tenemos permitido colaborar con un proyecto ya existente podemos crear un ***fork*** en el sitio del repositorio online. Así tendremos una copia del proyecto original a la cual le podremos hacer los cambios que queramos. Y podemos realizar ***pull requests*** (pedidos de modificación) a los administradores del proyecto original para que puedan agregar nuestros cambios si así lo deciden.
