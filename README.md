# Trabajo individual 
Jhonny Leonardo Rivas Olivera
## Clase 1
### ¿Que es Git? 
Es un sistema de control de versiones distribuido (VCD)
El mismo no guarda archivos, si no la versiones del mismo a lo largo del tiempo localmente.
### ¿Como nacio Git ?
Linus Torvals esta utilisando BitKeeper, el cual tenia una pequeña reglita  "No seras tu ni tus colaboradores ademass de mi ", hasta que alguien rompio la regla y le quitaron el acceso a Linus ,el cual se enfado mucho y en decidio hacer su propia version y se encerro durante dos semanas y creo Git,"Yo creo mis propias opciones.jpg" 
### ¿Como instalar Git ?
Para instalar git lo unico que es necesario es entrar a https://git-scm.com/install/  y seguir los pasos de instalacion acorde a tu S.O(Sistema Operativo) y verificas poniendo en la terminal git --version
### Configuraciones básicas 
´´´
git config --global user.name "Tu Nombre"
git config --global user.email "tu@correo.com"
git config --global core.autocrlf true
´´´
### Archivos que toda Repo debería tener 
README.md
.gitignore

## Clase 2 States y commits
### Los estados de git 
Directorio del trabajo (modificado)
Stage Area (preparado)
Repositorio local (confirmado)

### Directorio del trabajo (modificado)
GIT observa tus archivos, y los cataloga en: 
Untracked: Sin seguimiento, que lo ve pero no tiene una
version antigua de este archivo, sucede cuando este es creado.

Modified: Es cuando GIT ya tiene una version previa del archivo y lo
modificaste, eliminaste o cambiaste de nombre.

Si quiero que un archivo vuelva a su estado original 
´´´
git restore <archivo>
´´´
###
###
###

