---
tags:
 - Git
#  - GitHub
#  - Bash
---

<!-- 
# Comandos Iniciales y Configuración Global

Recomendado: usar la terminal Git Bash para trabajar.

Información de la versión instalada:
```bash
git --version
```
 -->


# Configuración global

Git requiere una serie de configuraciones preliminares en la estación de trabajo para funcionar correctamente.


## Usuario

Ponemos nuestro nombre o apodo a nuestra estación de trabajo:
```bash title="user"
git config --global user.name nombre_usuario
```

También declaramos nuestro email: 

```bash title="email"
git config --global user.email   nombre_usuario@servidor_correo
```

Este mail es meramente informativo y no se revisa su disponibilidad.

## Editor por defecto

Se selecciona el editor de texto preferido y la terminal queda en espera hasta que el editor usado se cierre.

```bash
git config --global core.editor  nombre_editor_texto --wait   
```

Ejemplos de editores: 


| Editor | Opción  |
| :---  |: ---   |
| VSCode | `code --wait`|
| VSCodium | `codium --wait` |
| Block de Notas | `notepad --wait`  |




## Fin de línea

Configura el salto de línea para los archivos según el sistema operativo:

=== "Windows"

    ```bash
    git config --global core.autocrlf  true
    ```

=== "Linux / MAC"

    ```bash
    git config --global core.autocrlf  input
    ```

Esta diferencia responde a que los caracteres ASCII usados para marcar el fin de línea no son los mismos para todos los sistemas operativos:

| Sistema operativo | Caracteres de salto línea | 
| :---: | :---: |
| Windows| CR LF| 
| Linux  | LF   | 
| MAC    | LF   | 


Es importante configurar el fin de línea para evitar conflictos de seguimiento con otras estaciones de trabajo.


## Archivo de configuración

El archivo `.gitconfig` (archivo oculto) guarda todas aquellas configuraciones modificadas por el usuario.


Este archivo se abre con el editor predefinido usando el comando:
```bash
git config --global -e
```


## Lista de configuraciones

La lista de configuraciones completa se obtiene con la opción `list`:

```bash
git config list
```

!!! hint "Regreso a comandos" 
    Se puede volver de las ventanas informativas a la ventana de comandos presionando la **letra ++q++**.

