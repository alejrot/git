


## [Volver al Indice](../Index.md#git)

<!-- <image src='./imagenes/git.png' alt="git" > -->

# GIT

## Comandos Iniciales y Configuración Global

Recomendado: usar la terminal Git Bash para trabajar.

Información de la versión instalada:
```bash
git --version
```
Ponemos nuestro nombre a nuestra estación de trabajo:
```bash
git config --global user.name “< nuestro nombre o apodo>”
```
Declaramos nuestro email. Es meramente informativo y no revisa su disponibilidad.
```bash
git config --global user.email   <usuario>@<servidor_correo>
```
Se selecciona por defecto el editor de texto indicado y la terminal queda en espera hasta que el editor usado se cierre.
```bash
git config --global core.editor  <editor_texto> --wait   
```
Ejemplos editores: 

- VSCode	    → code --wait  
- VSCodium	    → codium --wait  
- Bloc de Notas → notepad --wait

Abre el archivo de configuración global:
```bash
git config --global -e
```
Configura el salto de línea para los archivos según el sistema operativo:
```bash
git config --global core.autocrlf   <valor>
```
- en Windows  se usa CR LF  (carriage return y line feed) → poner true
- en Linux sólo LF  → poner input
- en MAC sólo LF    → poner input
Configurar para evitar conflictos con otras estaciones de trabajo.

Resumen de configuraciones:
```bash
git config -h
```

**HINT:** se puede volver de las ventanas informativas a la ventana de comandos presionando la letra Q.


## Comandos de los directorios (simil Linux)
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
**HINT:** escribir el nombre parcialmente y presionar TAB para autocompletar.

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

## Etapas GIT

### 1. Stage
Es una etapa intermedia dentro del computador donde el usuario decide qué archivos añadir (ó quitar) y donde se guardan los cambios preliminares realizados sobre los mismos. Utiliza la instrucción add para registrar los archivos y sus cambios.

### 2. Commit
Etapa donde se actualizan (guardan) los cambios hechos en los archivos del proyecto y se incorpora la numeración y una descripción de las modificaciones realizadas. Utiliza la instrucción commit para crear puntos de guardado del proyecto también llamados commit.

### 3. Server
Destino final de los archivos cuando se trabaja en equipo y/o el proyecto es público. Usa la instrucción push.



## Usando GIT
Crea un repositorio GIT en la ubicación actual (archivos y carpetas ocultos):
```bash
 git init
```
La subcarpeta oculta *.git* **no** se comparte a los otros desarrolladores.

Abre el programa de edicion elegido en el directorio actual:
```bash
EDITOR .
```
ej: abrir  VSCode en el directorio del proyecto
```bash
 “code .”  
```

Añade a GIT  los cambios realizados hasta el momento del archivo especificado únicamente.
```bash
git add <nombre_archivo>
```
Añade a GIT la carpeta completa indicada:
```bash
git add <nombre_directorio>
```
Añade a GIT las modificaciones de todos los archivos indicados:
```bash
git add <nombre_archivo1>  <nombre_archivo_2>  [...]
```

Añade a GIT todos los archivos terminados en la extension indicada:
```bash
git add  *.<extension_archivo>
```
Ejemplo:
```bash
git add *.txt
```
Añade todos los archivos existentes:
```bash
git add .
git add -A
```
Es una mala práctica porque puede añadir al proyecto archivos ajenos al programa: binarios, imágenes de entrada, archivos de salida del programa, etc.

Resumen del proyecto: rama utilizada actualmente por GIT , actualizaciones realizadas del proyecto y archivos incluidos , distinguiendo los ya guardados y los que tienen cambios pendientes de guardado.

```bash
git status
```
Muestra solamente los archivos del proyecto indicando cuales están alterados y guardados y cuáles no:
```bash
git status -s
```
Indica qué cambios fueron realizados en cada archivo alterado: 
```bash
git diff
```
Este comando indica qué contenido se añadió y qué contenido se quitó. Sólo muestra cambios pendientes de guardar en el proyecto. Se sale con la **tecla Q**.

Indica qué cambios fueron realizados en cada archivo alterado pero esta vez ya fueron guardados en el proyecto y listos para comprometer:
```bash
git diff --staged
```
Compromete (actualiza) los cambios realizados al proyecto:
```bash
git commit -m “breve_descripción”
```
Este crea una especie de punto de guardado al cual se puede volver posteriormente con una descripción añadida por el usuario entre comillas. También asigna un número de clave identificadora para este punto de guardado. Va precedido por el comando *add*:
```bash
git add <archivo>
git commit -m “breve_descripción”
```
Una alternativa resumida para trabajar con archivos previamente añadidos es usar directamente la opcion *-am*: 
```bash
git commmit -am “breve_descripción”
```

Elimina el archivo de proyecto indicado (puede revertirse)
```bash
git rm <nombre_archivo>
```
Recupera el archivo de proyecto indicado (último estado).
```bash
git restore <nombre_archivo>
```
Recupera el archivo de proyecto indicado (última versión añadida al proyecto).
```bash
git restore  --staged <nombre_archivo>
```
Mueve, renombra y añade la copia del archivo al proyecto.
```bash
git mv  <nombre_archivo>  <nuevo_nombre_archivo>
```
Hace que GIT deje de seguir los cambios del archivo indicado.
```bash
git reset HEAD <nombre_archivo>
```
Hace que GIT deje de seguir todos los archivos del directorio.
```bash
git reset HEAD
```
Historial de los commits realizados:
```bash
git log
git log --oneline
```
muestra una lista en orden de los commit realizados, su número clave y su descripción realizada. Los cambios más recientes aparecen primero. Se sale con la **tecla Q**.

## Variables de Entorno

Las variables de entorno (usuarios, contraseñas, bases de datos etc) NO deben compartirse en GIT.
Nombre de archivo habitual para variables entorno:  ***.env*** (archivo oculto)

Puede crearse un archivo de excepciones :  .gitignore , un archivo oculto donde se indican los archivos y rutas a ignorar por GIT.
```bash
touch .gitignore
```
Es posible crear el archivo desde la terminal. El archivo se puede editar con un editor de texto donde se indica renglón a renglón cada archivo y directorio a ignorar por GIT. Formato:
```bash
<nombre_archivo>
<nombre_carpeta>/
<nombre_carpeta>/<nombre_subcarpeta>/
```

Se sube al proyecto el archivo de excepciones:
```bash
git add .gitignore
```
Si todo salió bien el comando status dejará de avisar sobre los archivos y carpetas ignorados.


## Branch (Bifurcación)

GIT permite manejar varias versiones paralelas (ramas) del proyecto mediante bifurcaciones.

Indicar qué rama del proyecto nos encontramos:
```bash
git branch
```
Al comienzo es en la principal (main), la única existente por defecto. En algunas versiones de GIT la rama principal es llamada master.

Crear una nueva rama con el nombre indicado 
```bash
git checkout -b  <nombre_nueva_rama>
```
*git* nos pasa a la nueva rama automaticamente.

Conmuta a la rama elegida del proyecto:
```bash
git checkout  <nombre_rama>
```
Renombrar una rama:
```bash
git branch -m <nombre_rama>  <nuevo_nombre_rama>
```
Ejemplo:  de master a main   
```bash
git branch -m master main
```

## Merge (Unión de Ramas)

Las versiones paralelas del proyecto pueden reunirse para recolectar los cambios realizados entre ellas.
```bash
git switch  <nombre_rama>
git checkout  <nombre_rama_definitiva>
```
Es preferible el comando 'switch' porque es más respetuoso del contenido que 'checkout'

Nos ubicamos en la rama que queremos actualizar y mantener.
```bash
git merge <rama_alterna>
```
Elegimos la rama de la que se leerán los cambios a añadir. Esta última NO dejará de existir sino que seguirá igual.

Eliminar la rama local seleccionada: opcion *-d*
```bash
git branch -d <nombre_rama>
```
 Requiere que ésta haya sido pusheada y fusionada con la rama remota.



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

## Git Stash
git no permite el cambio de rama si los archivos tienen modificaciones no registradas.
El comando 'stash' permite hacer guardados temporales para poder pasar a trabajar en otras ramas del proyecto sin recurrir a guardados definitivos adicionales con código defectuoso o incompleto.

Guardado temporal:
```bash
git stash 
```
Cambio de rama:
```bash
git switch <nombre_rama>
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


## Restaurar Archivos 

Para deshacer los cambios hechos sobre un archivo preguardado con el comando 'add':
```bash
git checkout -- <archivo>   #deshace cambios no 'added'
```
Para descartar también los cambios preguardados sobre el archivo y volver a su ultimo 'commit':
```bash
# MAL: si el archivo fue 'added' no vuelve al commit

git restore <archivo>  # descarta cambios respecto del último estado guardado ('add' o 'commit') 
git restore --staged <archivo>   # descarta el 'add' y sus cambios
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


## Alias de comandos Git

Se pueden **crear alias** para los comandos más usados
```bash
git cofig --global alias.<apodo> <comandos>
```
Ejemplo: crear un comando 'unstage' para descartar cambios de archivo
```bash
# Recomendado: crear comando'unstage'
git config --global alias.unstage 'reset  HEAD --'
```
Ahora estas dos instrucciones son equivalentes:
```bash
git unstage <archivo>
git reset HEAD <archivo>
```
**Recomendado:** crear un comando'tree' para visualizar los commits
```bash
# Recomendado: crear comando 'tree'
git config --global alias.tree "log --graph --decorate --all --oneline" 
```

## Git Diff
Marcar cambios respecto al último guardado_
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

## GitHub Pages

https://pages.github.com

GitHub permite crear un sitio web con subdominio de github en base a los archivos md de cada repositorio

https://docs.github.com/es/pages




## Colaboradores Remotos en GIT
https://desarrolloweb.com/articulos/git-clone-clonar-repositorio.html

https://git-scm.com/book/es/v2/Fundamentos-de-Git-Trabajar-con-Remotos

----
*******
___

[Hola Mundo ](https://www.youtube.com/watch?v=VdGzPZ31ts8)

[Curso de GIT y GITHUB desde CERO para PRINCIPIANTES - Brais Moure](https://www.youtube.com/watch?v=3GymExBkKjE)

https://www.freecodecamp.org/espanol/news/como-borrar-una-branch-de-git-en-ambos-repositorios-local-y-remoto/#:~:text=Borrar%20una%20branch%20LOCAL&text=Borra%20una%20branch%20local%20con%20git%20branch%20-d%20.&text=La%20opción%20-d%20eliminará%20la,sido%20empujada%20o%20fusionada%20aún.

https://komodor.com/learn/how-to-fix-fatal-remote-origin-already-exists-error/

https://desarrolloweb.com/articulos/descartar-cambios-archivos-git.html


https://keepcoding.io/blog/como-deshacer-y-rehacer-cambios-en-git/#:~:text=Si%20requieres%20regresar%20a%20alguna,%2C%20–mixed%20y%20–soft.

https://www.lachicainformatica.com/2020/06/git-volver-a-commit-anterior-viajes-en-el-tiempo.html



---
---

## [Volver a Inicio](#git)

## [Volver al Indice](../Index.md#git)





