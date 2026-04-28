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
Para que Git no vea ciertos archivos, se debe agregar su nombre completo al archivo 
gitignore

### Uso Stage Area
Comandos de agregado: 
´´´
git add <archivo>
´´´
 agrega un archivo específico, mientras que
 ´´´
  git add . 
  ´´´
  agrega todos los archivos observados.  


Sacar archivos: Si necesitas quitar un archivo del stage area y volver al estado anterior, usa 
´´´
git restore --staged <archivo>
´´´
### El Repositorio Local y Commits
Confirmación: Es la fase donde se crea el "punto de guardado" definitivo mediante
´´´
 git commit -m "mensaje".  
´´´

Deshacer: Para revertir el último commit realizado, se utiliza el comando 
´´´
git reset --soft HEAD~1
´´´
### Buenas Prácticas de Commits
Commits Atómicos: Cada confirmación debe representar un único cambio lógico, pequeño y completo. 

Frecuencia: Es mejor hacer commits pequeños y a menudo que uno solo con demasiados cambios, siempre que el proyecto siga funcionando.  

Escritura efectiva: * Usa verbos imperativos como Add (añadir), Change (modificar), Fix (arreglar) o Remove (eliminar).  No uses punto final ni puntos suspensivos en el mensaje.  Mantén el título en un máximo de 50 caracteres.  

Commits Semánticos: Usa prefijos para que el historial sea legible,

Prefijos:
feat: para una nueva característica para el usuario.

fix: para un bug que afecta al usuario.

perf: para cambios que mejoran el rendimiento del sitio.

build: para cambios en el sistema de build, tareas de 
despliegue o instalación.

ci: para cambios en la integración continua.

docs: para cambios en la documentación.

refactor: para refactorización del código como cambios de nombre de variables o funciones.

style: para cambios de formato, tabulaciones, espacios o puntos y coma, etc; no afectan al
usuario.

test: para tests o refactorización de uno ya existente




