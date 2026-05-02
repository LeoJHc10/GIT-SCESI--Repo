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
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@correo.com"
git config --global core.autocrlf true
```
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
```bash
git restore <archivo>

```
Para que Git no vea ciertos archivos, se debe agregar su nombre completo al archivo 
gitignore

### Uso Stage Area
Comandos de agregado: 
```bash
git add <archivo>
```
 agrega un archivo específico, mientras que
 ```bash
  git add . 
 ```
  agrega todos los archivos observados.  


Sacar archivos: Si necesitas quitar un archivo del stage area y volver al estado anterior, usa 
```bash
git restore --staged <archivo>
```
### El Repositorio Local y Commits
Confirmación: Es la fase donde se crea el "punto de guardado" definitivo mediante
```bash
 git commit -m "mensaje".  
```

Deshacer: Para revertir el último commit realizado, se utiliza el comando 
```bash
git reset --soft HEAD~1
```
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

## Clase 3 GITHUB Y SSH 

### ¿Git hub que es?
Es una plataforma en la nube que gestiona , aloja y colabora en proyectos de software utilizando
Git.

### SSH vs HTTPS
HTTPS :nos pide autentificacion constantemenete  
```bash
 https://github.com/user/repo.git
``` 
SSH: Se configura la computadora  ssh para comunicar con git hub.
para configurar se usa este codigo :

```bash
ssh-keygen -t ed25519 -C “tu-correo@email.com”    

``` 
### Para crear repositorio 
```bash
https://github.com/Tu-user  y hacer click en "New"

``` 
Pones nombre en el repositorio y le das “Create Repository”

### Conectar repositorio local de Git con uno en Github 
```bash
git remote add origin git@github.com:TuUser/TuRepo.git

git branch -M main

git push -u origin main
```
NOTA: ya lo tienes que tener inicializado
(git init) y con un commit 

### Clonar un repositorio de GIT

```bash
git clone “git@github...”}

```
### Cambios 
Subir mis cambios
```bash
git push origin <rama>


git push: "Empujar" mis
commits.
origin: ¿A dónde? Al servidor que apodamos "origin" (GitHub).
<rama>: ¿Qué rama? La rama
<rama> de mi código.
```
 Bajar los cambios hechos
```bash
git pull origin <rama>

git pull     trae los commits del servidor.
origin       ¿De dónde? Del servidor que apodamos "origin" (GitHub).
<rama>: ¿Qué rama? La rama
<rama> de mi código
```

tune
## Clase 4 

### Gestión de Repositorios Remotos (git remote)
Permite administrar la conexión entre tu PC y la nube:
```bash
git remote -v: Lista las URLs vinculadas.

git remote add <nombre> <url>:       Crea un nuevo vínculo  

git remote set-url <nombre> <url>:   Actualiza la dirección de un vínculo existente.
```


### Configuración de Múltiples Cuentas SSH
Para usar varias cuentas sin conflictos, se utilizan alias:

Generar llaves únicas:
```bash
ssh-keygen -t ed25519 -f ~/.ssh/id_nombre_cuenta.

```

Configurar el archivo SSH 
Define un Host único para cada cuenta:

```bash

Host github-personal
  HostName github.com
  IdentityFile ~/.ssh/id_personal
Clonar con el Alias:
git clone git@github-personal:usuario/repo.git.
```

### Configuraciones Locales e Identidad
Las configuraciones dentro de un repositorio mandan sobre las globales:
```bash
git config user.name "Nombre": Define el autor local.

git config user.email "correo@email.com": Define el correo local.
```


### Navegación y Control (git checkout)
Sirve para viajar en el tiempo o cambiar de contexto:
```bash
git checkout <hash>: Inspecciona un punto antiguo del historial.

git checkout <rama>: Regresa a la versión más reciente de una rama.

git checkout -b <nueva-rama>: Crea una rama a partir del punto actual para guardar experimentos.
```

## Clase 5 

###   Que son las ramas 
Las ramas permiten segmentar el desarrollo para trabajar de forma segura:

Rama main: Representa el tronco principal y contiene la versión estable y terminada del proyecto.

Ramificaciones: Funcionan como líneas temporales paralelas para experimentar o desarrollar funciones sin alterar el código base.

### Navegación entre Ramas
Existen dos formas principales de moverse entre estas líneas de tiempo:

```bash

git switch -c <nombre>: Comando moderno diseñado específicamente para crear y saltar a una rama nueva.

git checkout <nombre>: El método tradicional; aunque es más versátil, para el cambio de ramas se recomienda usar preferentemente switch.
```

### Metodología Gitflow
Es una estructura organizada que asigna roles específicos a cada rama para profesionalizar el ciclo de vida del software:

Ramas de Larga Duración
main: Reservada exclusivamente para el código que está en producción (listo para el usuario final).

develop: El espacio central donde se integran y prueban todas las mejoras antes de ser lanzadas.


### Ramas de Apoyo (Temporales)
feature/: Se utilizan para construir características o funcionalidades específicas.

release/: Destinadas a la limpieza final y preparación antes de una nueva versión oficial.

hotfix/: Canales de emergencia para corregir errores críticos encontrados en la rama de producción.

Resumen del ciclo: El trabajo diario ocurre en develop, y una vez validado, se traslada a main para su publicación oficial.

## Clase 6 
### Sincronización con el Remoto
```bash
git fetch: Consulta y descarga la información de los cambios en el servidor sin modificar tus archivos locales.

git pull: Descarga y aplica automáticamente los cambios del repositorio remoto en tu rama actual.

git push: Envía tus commits locales al repositorio remoto.

Usa el flag -u la primera vez que subas una rama a un repositorio ajeno.
```
### Integración de Cambios (git merge)
Concepto: Fusiona el historial de una rama en otra.

Recomendación: Usa el flag --no-ff (no fast forward) para mantener rastro visual de la rama en el historial, incluso si decides borrarla después.

### Ciclo de Trabajo Estándar (Sin Pull Requests)
Actualización Inicial:

Sitúate en la rama de integración (develop).
```bash
Ejecuta git fetch y git pull para estar al día.
```


Desarrollo en Rama Propia:

Cámbiate a tu rama de trabajo e integra cambios de develop si los hubo mediante un merge.
```bash
Trabaja y sube tus avances con git push.
```


Fusión Final:

Regresa a develop y asegúrate de que siga actualizada.
```bash
Fusiona tu trabajo usando git merge --no-ff mi-rama.
```


Si hay conflictos, resuélvelos manualmente, añade los archivos con git add . y finaliza con git commit.

Limpieza:

Elimina la rama local con git branch -D y sube la rama develop actualizada al remoto.

```bash
```
