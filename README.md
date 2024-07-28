# Investigacion-aplicada-1

## Capítulo 1: Introducción a Git.

### 1.1 ¿Qué es Git?
Git es un sistema de control de versiones distribuido, creado por Linus Torvalds en 2005, que permite a los desarrolladores rastrear los cambios en el código fuente durante el desarrollo del software. Es una herramienta esencial para la colaboración en proyectos, ya que facilita la gestión de múltiples versiones del código de manera eficiente y segura.

### 1.2 Importancia del Control de Versiones.
*El control de versiones es fundamental en el desarrollo de software por varias razones:*

- Historial de Cambios: Permite mantener un registro completo de todas las modificaciones realizadas en el código, facilitando la identificación y corrección de errores.
- Colaboración: Facilita el trabajo en equipo, permitiendo que varios desarrolladores trabajen en el mismo proyecto sin interferencias.
- Reversión de Cambios: Permite revertir el código a versiones anteriores en caso de que se introduzcan errores.
- Seguridad y Recuperación de Datos: Actúa como un sistema de copias de seguridad, protegiendo contra la pérdida de datos.

### 1.3 Características Claves de Git.
- Distribuido: Cada desarrollador tiene una copia completa del repositorio, incluyendo todo el historial de cambios.
- Eficiencia: Optimizado para manejar grandes proyectos con eficiencia.
- Flexibilidad: Soporta diversos flujos de trabajo y modelos de desarrollo.
- Seguridad: Utiliza una tecnología de hashing (SHA-1) para asegurar la integridad del historial.

### 1.4 Instalación de Git.
*Para comenzar a usar Git, es necesario instalarlo en tu sistema. Git está disponible para múltiples sistemas operativos:*
- Windows: Se puede instalar usando el instalador de Git for Windows.
- macOS: Puede ser instalado mediante Homebrew (brew install git).
- Linux: Usualmente está disponible en los repositorios de las distribuciones (sudo apt-get install git para Debian/Ubuntu, sudo yum install git para Fedora/RedHat).

## Capítulo 2: Flujo de Trabajo Básico.

### 2.1 Crear un Repositorio.
*El primer paso en Git es crear un nuevo repositorio o clonar uno existente. Un repositorio es una estructura de almacenamiento donde se mantienen los archivos del proyecto y su historial de cambios.*
- Inicializar un nuevo repositorio: 'git init'
- Clonar un repositorio existente: 'git clone <url_del_repositorio>'

### 2.2 Realizar Cambios y Commit.
*Una vez que tienes un repositorio, puedes comenzar a realizar cambios en los archivos y guardar esos cambios con commits.*
- Agregar archivos al área de preparación: 'git add <archivo>'
- Hacer un commit: 'git commit -m "Mensaje del commit"'

### 2.3 Visualizar el Historial de Cambios.
Para ver el historial de commits en el repositorio, se utiliza el comando:
- 'git log'

### 2.4 Administrar Ramas (Branches).
*Las ramas permiten trabajar en diferentes versiones del proyecto simultáneamente.*
- Crear una nueva rama: 'git branch <nombre_de_la_rama>'
- Cambiar de rama: 'git checkout <nombre_de_la_rama>'
- Crear y cambiar a una nueva rama: 'git checkout -b <nombre_de_la_rama>'

### 2.5 Fusionar Cambios.
*Para integrar cambios de una rama en otra, se usa el comando merge:*
- Fusionar una rama: 'git merge <nombre_de_la_rama>'

### 2.6 Resolver Conflictos.
Si hay conflictos durante la fusión de ramas, Git te pedirá que resuelvas los conflictos manualmente. Después de resolverlos, se realiza un commit para finalizar la fusión.

## Capítulo 3: Gestión de ramas.

### 3.1 Introducción a las Ramas.
Las ramas en Git son una característica esencial que permite a los desarrolladores trabajar en diferentes líneas de desarrollo simultáneamente. Cada rama es una bifurcación de la línea de desarrollo principal que permite experimentar, agregar nuevas características o corregir errores sin afectar la base de código principal hasta que esté listo para ser fusionado.

### 3.2 Creación de Ramas.
*Para crear una nueva rama en Git, se utiliza el comando 'git branch'. Este comando crea una nueva rama a partir de la rama actual sin cambiar a ella inmediatamente.*
- Crear una nueva rama: 'git branch <nombre_de_la_rama>'

*Para crear una nueva rama y cambiar a ella inmediatamente, se puede combinar los dos comandos anteriores en uno solo:*
- Crear y cambiar a una nueva rama: 'git checkout -b <nombre_de_la_rama>'

### 3.3 Cambio de Ramas.
*Una vez creada la nueva rama, se puede cambiar a ella usando el comando 'git checkout'.*
- Cambiar a una rama existente: 'git checkout <nombre_de_la_rama>'

### 3.4 Listado de Ramas.
*Para ver una lista de todas las ramas en el repositorio, se usa el comando 'git branch'. Las ramas locales aparecerán sin prefijo, mientras que las ramas remotas aparecerán con el prefijo 'remotes/' .*
- Listar todas las ramas locales: 'git branch'
- Listar todas las ramas, incluidas las remotas: 'git branch -a'

### 3.5 Fusión de Ramas (Merge).
*Una vez que se ha completado el trabajo en una rama, es posible fusionarla con otra, generalmente la rama principal ('main' o 'master'). La fusión de ramas combina los cambios de la rama de origen con la rama de destino.*
- Fusionar una rama en la rama actual: 'git merge <nombre_de_la_rama>'

### 3.6 Resolución de Conflictos.
Durante la fusión, pueden surgir conflictos si los cambios en las ramas afectan las mismas líneas de código. Git marca estos conflictos y el desarrollador debe resolverlos manualmente.
- #### Pasos para resolver conflictos:
       1. Abrir los archivos conflictivos en un editor de texto.
       2. Buscar los marcadores de conflicto ('<<<<<<<', '=======', '>>>>>>>').
       3. Editar el contenido para resolver el conflicto.
       4. Una vez resueltos, añadir los archivos resueltos: 'git add <archivo_resuelto>'
       5. Completar la fusión con un commit: 'git commit'

### 3.7 Eliminación de Ramas.
Una vez que una rama ha sido fusionada y ya no es necesaria, puede ser eliminada para mantener el repositorio limpio.
- Eliminar una rama local: 'git branch -d <nombre_de_la_rama>'
- Eliminar una rama remota: 'git push origin --delete <nombre_de_la_rama>'

### 3.8 Estrategias de Ramas.
*Diferentes proyectos pueden usar diferentes estrategias de ramas según sus necesidades. Algunas de las estrategias más comunes incluyen:*
- Git Flow: Una estrategia estructurada con ramas dedicadas para desarrollo, lanzamiento y producción.
- GitHub Flow: Una estrategia simplificada utilizada por GitHub, basada en ramas de características que se fusionan directamente en 'main'.
- Feature Branching: Cada nueva característica o corrección de errores se desarrolla en su propia rama y se fusiona en la rama principal una vez completada.

### 3.9 Rebase.
*El rebase es otra técnica para integrar cambios de una rama a otra, reescribiendo el historial de commits para producir un historial más lineal y limpio.*
- Rebase de una rama sobre otra: 'git rebase <rama_base>'

El rebase puede ser útil para mantener un historial de commits limpio, pero debe usarse con cuidado para evitar complicaciones, especialmente cuando se trabaja con ramas compartidas por varios desarrolladores.

### 3.10 Buenas Prácticas.
- Nombrar Ramas Claramente: Usar nombres descriptivos y consistentes para las ramas.
- Commits Pequeños y Frecuentes: Realizar commits con cambios pequeños y bien documentados.
- Revisar y Probar Antes de Fusionar: Revisar el código y probar los cambios antes de fusionar una rama en la rama principal.

## Capítulo 4: Repositorios Remotos.

### 3.1 ¿Qué son los Repositorios Remotos?
Un repositorio remoto es una versión del proyecto que está alojada en un servidor en internet o en una red local. Los repositorios remotos facilitan la colaboración entre equipos, permitiendo que múltiples desarrolladores trabajen en el mismo proyecto.

### 3.2 Configuración de Repositorios Remotos.
*Para trabajar con repositorios remotos, es necesario configurar las URL de los repositorios.*
- Agregar un repositorio remoto: 'git remote add origin <url_del_repositorio>'
- Ver los repositorios remotos: 'git remote -v'

### 3.3 Sincronización con Repositorios Remotos.
*Los comandos clave para sincronizar los cambios con los repositorios remotos incluyen push y pull:*
- Enviar cambios al repositorio remoto: 'git push origin <nombre_de_la_rama>'
- Obtener cambios del repositorio remoto: 'git pull origin <nombre_de_la_rama>'

### 3.4 Clonar Repositorios Remotos.
*Clonar un repositorio remoto crea una copia local completa del mismo, incluyendo todo su historial de cambios:*
- 'git clone <url_del_repositorio>'

### 3.5 Colaboración y Gestión de Contribuciones.
En equipos grandes, es común usar pull requests para gestionar contribuciones. Los desarrolladores crean ramas, realizan cambios y envían pull requests para que sus cambios sean revisados e integrados en la rama principal.

### 3.6 Seguridad y Acceso.
Es fundamental gestionar el acceso a los repositorios remotos. Git permite configurar permisos y autenticación para asegurar que solo las personas autorizadas puedan realizar cambios.
