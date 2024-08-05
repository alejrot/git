




# GIT

## Comandos de los directorios (Bash)
Archivos del actual directorio (sólo visibles)
```bash
ls
```
Archivos del actual directorio (sólo visibles)
```bash
ls -a
```
Directorio actual 
```bash
pwd
```
Permite entrar a un sub directorio
```bash
cd nombre_carpeta
```
!!! tip "HINT: autocompletado de nombres" 
    Escribir el nombre de archivos y carpetas parcialmente y entonces presionar TAB para autocompletar.

Permite retroceder al directorio superior.
```bash
cd ..
```
Permite entrar a una carpeta específica existente.
```bash
cd ‘ruta_de_carpeta’
```
Crea un nuevo directorio con el nombre indicado dentro de la ubicación actual.
```bash
mkdir mi_carpeta
```
Elimina el archivo especificado dentro del directorio.
```bash
rm  nombre_archivo
```
Mueve (y renombra) el archivo indicado
```bash
mv  <nombre_archivo>  <nuevo_nombre_archivo>
```
Lee y muestra en pantalla el contenido de archivo indicado.
```bash
cat <nombre_archivo>
```

Crea un archivo vacío con el nombre indicado:
```bash
touch <nombre_archivo>
```

## Etapas del repositorio GIT

### 0.Untracked
En la primera instancia del proyecto no hay seguimiento de carpetas ni de archivos.


### 1. Stage
Es una etapa intermedia dentro del computador donde el usuario decide qué archivos añadir (ó quitar) y donde se guardan los cambios preliminares realizados sobre los mismos. Utiliza la instrucción `add` para registrar los archivos y sus cambios.

### 2. Commit
Etapa donde se actualizan (guardan) los cambios hechos en los archivos del proyecto y se incorpora la numeración y una descripción de las modificaciones realizadas. Utiliza la instrucción `commit` para crear puntos de guardado del proyecto también llamados commit.

### 3. Server
Destino final de los archivos cuando se trabaja en equipo y/o el proyecto es público. Usa la instrucción `push`.




------

Mueve, renombra y añade la copia del archivo al proyecto.
```bash
git mv  <nombre_archivo>  <nuevo_nombre_archivo>
```


-----



## Compartir proyecto en un servidor
```bash
git remote add origin <URL/directorio/nombre_proyecto>
```
Indicamos la dirección web del servidor que alojará el proyecto y nuestro directorio.

Ejemplo típico :

    https://github.com/MI_USUARIO/MI_PROYECTO


Sube los cambios realizados al servidor tras crear en él la rama indicada (opción -u):
```bash
git push -u origin nombre_rama
```

**Importante:** en el servidor  la rama main/master NO está creada por defecto.

Eliminar la rama remota elegida:
```bash
git push remote  --delete <nombre_rama>
```
Elimina las ramas locales que ya no estén en el repositorio remoto:
```bash
git fetch -p 
```
Crea la rama “master” en el repositorio del servidor y sube los archivos al repositorio:
```bash
git push --set-upstream origin master
```
Permite subir las nuevas versiones del proyecto al servidor:
```bash
git push
```
Descarga las nuevas versiones desde el repositorio remoto al local:
```bash
git pull
```
A veces es necesario usarlo para  “unir” la rama remota con la actual del proyecto. 

```bash
git fetch
```
Similar a pull  pero creando una rama alterna en nuestra estación de trabajo.

## Generar token
El servidor nos pedirá un usuario y contraseña.En github esta última se obtiene así:

- Pestaña *Settings → Developer Settings → Personal Access Tokens → Generate New Token* ; 
- Creamos un *nombre* para el token e indicamos sus permisos; 
- Finalizamos clickeando *Generate Token*, esto crea el token y una contraseña al final. Clickeando en ella se copia al portapapeles y luego se pega en la terminal de trabajo.




## Como corregir errores de origen

Si aparece el error de subida porque “ el origen remoto ya existe” podemos escribir:
```bash
git remote -v
```
Permite saber a qué URL apunta el puntero origen (origin)
```bash
git remote remove origin
```
Elimina la URL ya cargada para poder empezar de nuevo.
```bash
git remote set-url origin <nueva_URL>
```
Asigna una nueva dirección web para reemplazar la antigua.
```bash
git remote rename origin <nuevo_puntero>
```
Cambia el nombre del puntero origin por uno distinto.




## Restaurar Archivos 

Para deshacer los cambios hechos sobre un archivo preguardado con el comando 'add':
```bash
git checkout -- <archivo>   #deshace cambios no 'added'
```
o:

```bash
git restore <archivo>  # descarta cambios respecto del último estado guardado ('add' o 'commit') 
```

Para descartar también los cambios preguardados sobre el archivo y volver a su ultimo 'commit':
```bash
# MAL: si el archivo fue 'added' no vuelve al commit

git restore --staged <archivo>   # descarta el 'add' y sus cambios
git restore <archivo>  # descarta cambios respecto del último estado guardado ('add' o 'commit') 
```
Otra opción:
```bash
git reset HEAD <archivo>  # MAL
```
Para restaurar todos los archivos al último 'commit' realizado:
```bash
git reset --hard
```
Otra opción es usar el comando revert:
```bash
git revert <id>
```

## Volver a los commit previos  (tiene varios errores )
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

**HINT:** el carácter ~ se obtiene escribiendo ‘AltGr’ +’4’
```bash
git reset --hard HEAD~<n>
```
Retrocedemos n posiciones de guardado, ocultando las posiciones posteriores.
```bash
git reset --hard HEAD <clave_commit>
```
Nos movemos al commit identificado por la clave. Puede ser un guardado posterior al HEAD actual. Oculta los commits posteriores al elegido como destino.
```bash
git reflog
```
Repasa el historial de guardados.
```bash
git reset --hard HEAD@{<indice>}
```
Nos mueve al guardado indicado por el número de índice (entero). El índice lo indica el comando git reflog. 

Saltar a un guardado particular:
```bash
git checkout <nombre_commit>
```
Seleccionar el actual punto de guardado como "head":
```bash
git checkout HEAD
```

## Clonar repositorios 
```bash
git clone <URL_del_proyecto>
```
Hace una copia completa del proyecto indicado desde el repositorio y la guarda en el directorio actual. 

Hay que instalar las dependencias, esto último depende del lenguaje de programación del proyecto. Cada lenguaje tiene sus propias prácticas y comandos. Recordar que el archivo .gitignore indica qué dependencias ignora GIT en el traspaso de los proyectos 

Si no tenemos permitido colaborar con un proyecto ya existente podemos crear un fork en el sitio del repositorio online. Así tendremos una copia del proyecto original a la cual le podremos hacer los cambios que queramos. Y podemos realizar pull requests (pedidos de modificación) a los administradores del proyecto original para que puedan agregar nuestros cambios si así lo deciden.


## Etiquetado
Listar etiquetas de un proyecto:

```bash
git tag
```
Listar etiquetas en base a un patrón (hay más de 500 en total):
```bash
git tag -l              #todas las etiquetas realizadas
git tag -l <patrón>
```
Asignar etiqueta al último commit:
```bash
git tag <etiqueta>
```
Ejemplo: numeracion para el ultimo commit:
```bash
git tag v1.0
```


Asigna un número de versión a un commit en base a su nombre
```bash
# REVISAR
git tag -a v<numero_version> -m <etiqueta>
```
Asigna un número de versión a un commit en base a su nombre.

Ejemplos:
```bash
git tag -a v1.0.0 -m “Primera versión ”
git tag -a v1.2.3 <codigo_commit>
```

Las etiquetas no se transmiten al repositorio remoto de forma automática sino que esto debe hacerse manualmente.

Para subir una etiqueta al repositorio remoto:
```bash
# etiqueta actual --> remoto
git push origin v<numero_version>
```
Para subir todas las etiquetas al repositorio remoto:
```bash
# etiquetas (todas) --> remoto
git push origin --tags
```

Las etiquetas nos permiten movernos a un punto de guardado específico. Si queremos movernos a un estado del proyecto indicado por su etiqueta se escribe:
```bash
git checkout tags/<etiqueta>
```

Las etiquetas pueden eliminarse. Para ello hacer:
```bash
# borrado de tags
git tag -d <etiqueta>               # repositorio local
git push --delete origin <etiqueta>    # repositorio remoto
```




## Diferencias - diff

Marcar cambios respecto al último guardado:
```bash
git diff
```
Comparar la rama actual con una alterna:
```bash
git diff <nombre_rama>
```

## Git Flow

Incluye un manejo simpificado de ramas prededefinidas ,con los siguientes roles:
- **main:** es la rama de producción , la rama del proyecto más testeada y confiable.
- **develop:** la rama de desarrollo, que es una bifurcación de main y a partir de ella se hacen los cambios del proyecto. Los merges se llevan a la rama main.
- **feature:** son una bifurcación de bifurcaciones de la rama develop dedicadas a desarrrollar caracteristicas específicas. De esta rama puede haber varias.
- **hotfix:** son bifurcaciones de la rama main para arreglos de emergencia y afecta al resto de las rama automáticamente.


## Git Cherry-Pick
Permite traer a la rama actual commits particulares:
```bash
git cherry-pick <nombre_commit>
```
Para traer los commits posteriores al elegido uno por uno se usa la posición 'continue':
```bash
git cherry-pick --continue
```
Es un comando riesgoso porque puede traer conflictos.

## Git Rebase

Se trae al presente una rama antigua seleccionada. Es un comando riesgoso.
```bash
git rebase <nombre_rama>
```
otras opciones:

```bash
git rebase -i
git rebase --continue
git rebase --abort
```





## Colaboradores Remotos en GIT
https://desarrolloweb.com/articulos/git-clone-clonar-repositorio.html

https://git-scm.com/book/es/v2/Fundamentos-de-Git-Trabajar-con-Remotos

----
*******
___
