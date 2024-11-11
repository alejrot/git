# Commits previos


<!-- # Volver a los commit previos  (tiene varios errores ) -->
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
