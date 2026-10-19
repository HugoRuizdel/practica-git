# Respuestas del Reto Final de Git

### a) ¿En qué se diferencian git restore y git revert?
* **`git restore`**: Se utiliza para descartar cambios locales que aún no se han confirmado (en el directorio de trabajo o área de preparación) o para recuperar archivos específicos de commits anteriores. Modifica el estado actual de los archivos de forma local.
* **`git revert`**: Se utiliza para deshacer un commit que ya ha sido realizado (y posiblemente subido al repositorio remoto), creando un **nuevo commit** que aplica los cambios inversos. Es seguro para repositorios compartidos porque no destruye ni altera el historial existente.

### b) ¿Por qué password.txt sigue siendo un problema aunque ya no aparezca en la última versión?
Porque aunque lo hayamos eliminado del seguimiento en la versión actual y hayamos añadido un `.gitignore`, **el archivo sigue grabado en el historial de commits anteriores** (en la base de datos de Git). Si alguien clona el repositorio o accede al historial de commits, podrá ver y extraer la contraseña fácilmente. Para eliminarlo por completo de todo el historial se requerirían herramientas avanzadas como `git filter-repo` o `BFG Repo-Cleaner`.

### c) ¿En qué se diferencian git rm y git rm --cached?
* **`git rm`**: Elimina el archivo tanto del control de versiones de Git como del disco duro de tu ordenador (lo borra físicamente).
* **`git rm --cached`**: Elimina el archivo del control de versiones de Git (deja de rastrearlo), pero **lo conserva intacto** en tu equipo.