


# GIT
<!-- 


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
-->


<!-- 
## Etapas del repositorio GIT

### 0.Untracked
Se crea un nuevo repositorio vacío con el comando `init`.
En esta primera instancia del proyecto no hay seguimiento de carpetas ni de archivos.


### 1. Stage
Es una etapa intermedia dentro del computador donde el usuario decide qué archivos añadir (ó quitar) y donde se guardan los cambios preliminares realizados sobre los mismos. Utiliza la instrucción `add` para registrar los archivos y sus cambios.

### 2. Commit
Etapa donde se actualizan (guardan) los cambios hechos en los archivos del proyecto y se incorpora la numeración y una descripción de las modificaciones realizadas. Utiliza la instrucción `commit` para crear puntos de guardado del proyecto también llamados commit.

### 3. Server
Destino final de los archivos cuando se trabaja en equipo y/o el proyecto es público. Usa la instrucción `push`.
 -->



------

Mueve, renombra y añade la copia del archivo al proyecto.
```bash
git mv  <nombre_archivo>  <nuevo_nombre_archivo>
```


-----


## Generar token
El servidor nos pedirá un usuario y contraseña.En github esta última se obtiene así:

- Pestaña *Settings → Developer Settings → Personal Access Tokens → Generate New Token* ; 
- Creamos un *nombre* para el token e indicamos sus permisos; 
- Finalizamos clickeando *Generate Token*, esto crea el token y una contraseña al final. Clickeando en ella se copia al portapapeles y luego se pega en la terminal de trabajo.








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
