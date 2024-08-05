


# Comandos Iniciales y Configuración Global

Recomendado: usar la terminal Git Bash para trabajar.

Información de la versión instalada:
```bash
git --version
```
Ponemos nuestro nombre a nuestra estación de trabajo:
```bash
git config --global user.name “<nombre o apodo de usuario>”
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

<!-- - VSCode	    → code --wait  
- VSCodium	    → codium --wait  
- Bloc de Notas → notepad --wait -->

| Editor | Opción  |
| :---  |: ---   |
| VSCode | code --wait|
| VSCodium | codium --wait |
| Block de Notas | notepad --wait  |


Abre el archivo de configuración global:
```bash
git config --global -e
```
Configura el salto de línea para los archivos según el sistema operativo:
```bash
git config --global core.autocrlf   <valor>
```



<!-- - en Windows  se usa CR LF  (carriage return y line feed) → poner true
- en Linux sólo LF  → poner input
- en MAC sólo LF    → poner input -->


Tabla de configuraciones:

| Sistema operativo | Salto línea | Opción |
| :---: | :---: |:---: |
| Windows| CR LF| `true`  |
| Linux  | LF   | `input` |
| MAC    | LF   | `input` |

CR: *carriage return*
LF: *line feed*


Configurar para evitar conflictos con otras estaciones de trabajo.

Resumen de configuraciones:
```bash
git config -h
```

!!! hint "HINT" 
    Se puede volver de las ventanas informativas a la ventana de comandos presionando la **letra Q**.

