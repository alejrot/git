---
tags:
 - Git
#  - GitHub
#  - Bash
---


# Etiquetado


Listar etiquetas de un proyecto:

```bash
git tag
```
Listar etiquetas en base a un patrón (hay más de 500 en total):
```bash
git tag -l              #todas las etiquetas realizadas
git tag -l patron
```
Asignar etiqueta al último commit:
```bash
git tag etiqueta
```
Ejemplo: numeracion para el ultimo `commit`:
```bash
git tag v1.0
```


Asigna un número de versión a un `commit` en base a su nombre
```bash
# REVISAR
git tag -a v{numero_version} -m etiqueta
```
Asigna un número de versión a un commit en base a su nombre.

Ejemplos:
```bash
git tag -a v1.0.0 -m “Primera versión ”
git tag -a v1.2.3  codigo_commit
```

Las etiquetas no se transmiten al repositorio remoto de forma automática sino que esto debe hacerse manualmente.

Para subir una etiqueta al repositorio remoto:
```bash
# etiqueta actual --> remoto
git push origin v{numero_version}
```
Para subir todas las etiquetas al repositorio remoto:
```bash
# etiquetas (todas) --> remoto
git push origin --tags
```

Las etiquetas nos permiten movernos a un punto de guardado específico. Si queremos movernos a un estado del proyecto indicado por su etiqueta se escribe:
```bash
git checkout tags/etiqueta
```

Las etiquetas pueden eliminarse. Para ello hacer:
```bash
# borrado de tags
git tag -d etiqueta                  # repositorio local
git push --delete origin etiqueta    # repositorio remoto
```


