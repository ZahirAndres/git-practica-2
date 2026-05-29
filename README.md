# git practica 2
Taller GIT. Práctica 2.
Guarda los comandos realizados, así como los resultados(capturas), integrarlo dentro del mismo repositorio

## Trabajar con un proyecto HTML y un repositorio local.
- Crea una carpeta practica-taller-git en tu pc.
- Inicializa el repositorio. 
 ```bash
 git init
 ```
- Crea el fichero index.html con un html simple.
- Comprueba que el repositorio a detectado el cambio. 
```bash
git status
```
- Añade el fichero al stage. 
```bash
git add index.html.
```
- Confirma los cambios. 
```bash
git commit -m “added index file”
```
- Añade un fichero description.html y edita index.html.
- Comprueba que ha detectado el nuevo fichero y la modificación de index.
```bash
git status
git diff
```
- Crea un fichero TODO.txt de tareas pendientes.
- Comprueba que git ha detectado el nuevo fichero. 
```bash
git status
```
- Ignora el fichero TODO.txt ya que es donde anotaremos nuestras tareas personales y no debe formar parte del proyecto. Para ello crea un fichero .gitignore con la linea TODO.txt.
- Comprueba que ya no detecta el nuevo fichero TODO.txt (si que detectara el .gitignore claro). 
```bash
git status
```
- Añade y confirma el .gitignore.
- Puedes continuar añadiendo ficheros html, css e imágenes para probar el repositorio.


## Haz un fork del repositorio creado para la práctica del taller:
- Entra en https://github.com/
- Accede a tu cuenta.
- Accede al repositorio del profesor https://github.com/lalobarri/git-practica-2.git
- Pulsa el botón fork (parte superior derecha) para crearte una copia del mismo en tu cuenta.
- Clona el repositorio en tu equipo *en otra carpeta diferente que la llamaremos 'git-practica-2'*. Quedará algo parecido a lo siguiente:
```bash
git clone https://github.com/[tu-nombre-de-usuario]/git-practica-2.git
```
- Crea un nuevo fichero en el proyecto que se llame [tu-nombre-de-usuario].html
- Edita el fichero añadiendo como título tu nombre, algún texto y lo que desees en el.
- Añade el fichero al repositorio.
- Súbelo al repositorio remoto (github). 
```bash
git push
```
- Crea una rama develop y cámbiate a ella.
```bash
git checkout -b develop
```
- Realiza cambios en el proyecto, confírmalos y súbelos al repositorio remoto.
```bash
git status
git add *
git commit -m "Mensaje del commit..."
git push origin
```
- Desde github crea un pull request de la rama develop a main.
- Fusiona la rama develop con en main. No deberías de tener ningún conflicto.
- Haz nuevos cambios en el proyecto siguiendo el flujo de trabajo git flow.

# Respuestas - Taller Git Práctica 2

**Alumno:** Zahir Andrés Rodríguez Mora  
**Grupo:** GIDS6082  
**Materia:** Ingeniería de Software — UTNG

---

## Preguntas y Respuestas

---

### 1. ¿Qué sucede cuando hacemos un `git add`?
**Respuesta:** Al ejecutar este comando, estás trasladando los cambios realizados en tu directorio de trabajo hacia el área de preparación, conocida como *staging area* o *index*. Este paso es fundamental para seleccionar qué archivos específicos deseas incluir en tu próxima instantánea. En esencia, estás preparando los archivos para que Git los tome en cuenta en el siguiente *commit*, pero aún no se han registrado formalmente en el historial.

### 2. ¿Qué sucede cuando hacemos un `git commit`? ¿Dónde está ese commit?
**Respuesta:** El comando `git commit` toma todos los cambios que habías puesto en el *staging area* y los graba de forma definitiva como una versión del proyecto. Git genera una captura de pantalla del estado del código, asignándole un identificador único (hash) junto con tus notas. Este registro se almacena internamente en la base de datos de Git, dentro de la carpeta oculta `.git` alojada localmente en tu equipo.

### 3. ¿Por qué al hacer `git commit` todavía no está disponible ese commit en el repositorio remoto?
**Respuesta:** Git es un sistema de control de versiones descentralizado. Por diseño, el repositorio en tu computadora funciona de manera independiente al repositorio en el servidor (GitHub). El comando `commit` solo actualiza el historial en tu máquina local. El servidor remoto no tiene visibilidad de estos cambios hasta que el usuario ejecute una acción de sincronización explícita.

### 4. ¿Qué hay que hacer para que veamos este commit en nuestro repositorio remoto de GitHub?
**Respuesta:** Debes utilizar el comando `git push`. Al ejecutar `git push origin <rama>`, le ordenas a Git que transfiera tus confirmaciones locales hacia el repositorio remoto configurado. Una vez que este comando finaliza correctamente, los cambios se replican en GitHub y quedan disponibles para ser vistos por otros colaboradores.

### 5. ¿Qué diferencia hay entre hacer un fork o crear una nueva rama?
**Respuesta:** * **Fork:** Es una acción que se realiza en la plataforma (GitHub) para crear una copia completa de un repositorio ajeno en tu propia cuenta. Es el método estándar para contribuir a proyectos de terceros sin tener permisos de escritura directos.
* **Rama (branch):** Es una bifurcación lógica dentro de tu propio repositorio. Te permite aislar líneas de desarrollo, permitiéndote experimentar o trabajar en nuevas funcionalidades sin afectar la estabilidad de la rama principal (*main*).

### 6. ¿Qué comando se utiliza para crear una nueva rama sin cambiarte a ella?
**Respuesta:** Se emplea `git branch <nombre_de_la_rama>`. Este comando genera la nueva referencia de rama, pero mantiene tu puntero de trabajo (*HEAD*) en la rama actual.

### 7. ¿Cuál es la diferencia entre los comandos `git switch` y `git checkout` al trabajar con ramas?
**Respuesta:** `git checkout` es un comando versátil y antiguo que, además de cambiar de rama, gestiona la restauración de archivos, lo que a menudo causa confusión. Por otro lado, `git switch` fue introducido en versiones recientes de Git con un enfoque exclusivo y claro: gestionar el cambio entre ramas, lo que lo vuelve una herramienta más específica y menos propensa a errores.

### 8. ¿Qué es una rama por defecto (como `main` o `master`) y por qué es importante?
**Respuesta:** Es la rama principal que Git crea al inicializar el repositorio. Se considera el centro neurálgico del proyecto y, convencionalmente, contiene el código más reciente y funcional. Su importancia radica en que sirve como base para todo el desarrollo y, usualmente, es la única que debe tener protecciones de escritura para garantizar la estabilidad del producto.

### 9. ¿Qué comando te permite ver la lista de todas las ramas locales de tu repositorio?
**Respuesta:** El comando `git branch` es el indicado para listar tus ramas locales. Si además necesitas visualizar tanto las locales como las que residen en el servidor remoto, debes añadir el parámetro `-a` (quedando como `git branch -a`).

### 10. En el contexto de Git, explica con tus propias palabras qué es una rama (branch) y cuál es su beneficio principal al trabajar en un proyecto de software
**Respuesta:** Una rama es básicamente un puntero móvil que sigue a tus commits, permitiéndote crear un flujo de trabajo paralelo. Su beneficio principal es la capacidad de desarrollar y probar funciones de forma aislada. Si una idea falla, simplemente descartas la rama y el proyecto principal permanece intacto. Además, permite que varios programadores colaboren en el mismo repositorio sin interferir en el avance de sus compañeros.

### 11. ¿Qué ha pasado con el contenido de la carpeta `practica-taller-git`? ¿Por qué no la podemos ver en nuestro repositorio remoto de GitHub?
**Respuesta:** Esta carpeta no es visible en GitHub porque, aunque iniciaste un repositorio local con `git init`, nunca se vinculó a una URL de un repositorio remoto mediante un comando como `git remote add origin`. Git no sabe que debe enviar esos archivos a ningún servidor, por lo que todo el trabajo permanece almacenado exclusivamente en tu disco duro.

---
