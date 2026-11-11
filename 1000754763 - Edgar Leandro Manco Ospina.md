1. ¿Qué es Git y qué problema resuelve?

Git es un sistema de control de versiones distribuido que permite llevar un registro de los cambios que se realizan en los archivos de un proyecto. Esto permite consultar las modificaciones que se han hecho, saber quién las realizó y recuperar versiones anteriores si ocurre algún problema. Al ser distribuido, cada persona tiene una copia del proyecto y de su historial en su computador, por lo que puede trabajar sin necesidad de estar conectado a internet.

Git ayuda a solucionar problemas como perder avances de un proyecto, cometer errores que afectan el código o tener varias copias de archivos con diferentes versiones sin saber cuál es la más reciente. También facilita el trabajo en equipo, ya que permite combinar los cambios realizados por diferentes personas y mantener un mejor control sobre las modificaciones del proyecto.


2. Diferencias entre Git y GitHub

Aunque Git y GitHub están relacionados, no son lo mismo porque cada uno tiene una función diferente.

- Git: Es un programa que nos permite llevar un control de los cambios que hacemos en un proyecto. Con él podemos guardar versiones, crear ramas y recuperar cambios anteriores.

- GitHub: Es una plataforma en línea donde podemos subir nuestros repositorios de Git, almacenarlos y compartirlos con otras personas.

También permite trabajar en equipo y revisar los cambios que se realizan en un proyecto.

Una analogía: Git es como el motor de un carro, y GitHub es como un parqueadero compartido con servicios extra donde guardas y compartes tu carro con otros. Se puede usar Git sin GitHub, pero no se puede usar GitHub sin Git.


3. ¿Qué es una nube de repositorios?

Es un servicio en internet donde se almacenan repositorios de Git en servidores remotos. Funciona como la copia central del proyecto: el equipo sube (push) sus cambios y descarga (pull) los de los demás desde ahí. Esto permite colaborar desde cualquier lugar, tener un respaldo del código si el computador falla y controlar quién puede ver o modificar el proyecto.

Alternativas a GitHub:

- GitLab: incluye CI/CD (integración y despliegue continuo) de forma nativa y se puede instalar en servidores propios.

- Bitbucket (de Atlassian): se integra muy bien con herramientas como Jira y Trello.

- Azure DevOps Repos (de Microsoft): muy usado en entornos empresariales.

- AWS CodeCommit o Gitea: otras opciones, la primera dentro del ecosistema de Amazon y la segunda ligera y de código abierto.


4. Glosario básico

- Commit (Confirmación o punto de control)

Es una “foto” o punto guardado del estado del proyecto en un momento determinado, acompañada de un mensaje que explica qué se cambió. Cada commit queda en el historial y permite volver a ese punto si es necesario.

Ejemplo: git commit -m "Agrego validación al formulario de registro"

- Branch (Rama)

Es una línea de desarrollo independiente que se separa de la principal para trabajar sin afectarla. Lo que se haga en la rama no cambia el código estable hasta que se decida unirlo.

Ejemplo: git branch login crea una rama llamada login, y git checkout login te cambia a ella para empezar a trabajar ahí.

- Merge (Fusión)

Es unir los cambios de una rama con otra, normalmente cuando se termina de desarrollar algo. Si dos ramas modificaron la misma parte del código, puede aparecer un conflicto que hay que resolver manualmente.

Ejemplo: estando en main, ejecutas git merge login para incorporar todo lo que hiciste en la rama login.

- Pull y Push

Push: envía tus commits locales al repositorio remoto para que otros puedan verlos.
Pull: trae los cambios que hay en el remoto y los integra en tu copia local.

Ejemplo: git push origin main sube tu trabajo a la nube; git pull origin main descarga lo que subieron tus compañeros.

- Pull Request (PR)

Es una solicitud para que los cambios de una rama se integren en otra (generalmente main o develop). Permite que el equipo revise el código, deje comentarios y lo apruebe antes de fusionarlo. Se crea en la plataforma (GitHub, GitLab), no directamente en Git.

Ejemplo: terminas la rama login, abres un PR hacia main, un compañero revisa tu código, pide un ajuste y finalmente lo aprueba.

- Clone (Clonar)

Es descargar una copia completa de un repositorio remoto a tu computador, incluyendo todo su historial y sus ramas. Además, deja configurado automáticamente el remoto de donde vino.

Ejemplo: git clone https://github.com/usuario/proyecto.git

- Upstream y Origin

Origin es el nombre por defecto del repositorio remoto del que clonaste, normalmente tu propio repositorio o el del equipo.
Upstream es el nombre que se suele dar al repositorio original cuando haces un fork (una copia propia) de un proyecto ajeno. Sirve para mantener tu fork actualizado con los cambios del proyecto original.

Ejemplo: haces fork de un proyecto de otra persona. Tu fork es origin y el repositorio original lo agregas como upstream con git remote add upstream https://github.com/autor-original/proyecto.git. Luego, con git pull upstream main traes sus novedades.


5. La importancia de las ramas

Las ramas son importantes porque nos permiten trabajar en diferentes partes de un proyecto sin afectar directamente la versión principal.

Por ejemplo, si necesitamos agregar una nueva función, podemos crear una rama y trabajar en ella. Cuando terminemos, podemos unir esos cambios con la rama principal.

Ventajas en el trabajo individual:
- Permiten realizar pruebas y modificaciones sin afectar el proyecto principal.

- Ayudan a mantener organizadas las diferentes funciones del proyecto.

- Facilitan el seguimiento de los cambios realizados.

Ventajas en el trabajo en equipo:

- Cada integrante puede trabajar en una rama diferente sin afectar el trabajo de los demás.

- Permiten revisar los cambios antes de agregarlos al proyecto principal.

- Facilitan la identificación y solución de errores.

- Permiten que varias personas trabajen al mismo tiempo en diferentes partes del proyecto.


6. ¿Qué es GitFlow?

GitFlow es una forma de organizar el trabajo con Git mediante diferentes ramas. Cada una tiene una función específica dependiendo de la etapa en la que se encuentre el proyecto.

Sus principales ramas son:
- master o main: Es la rama principal, donde se mantiene la versión estable del proyecto.

- develop: Es donde se van uniendo las nuevas funciones que se desarrollan antes de preparar una nueva versión.

- feature: Son ramas que se crean para trabajar en nuevas funciones sin modificar directamente el proyecto principal.

- release: Se utiliza cuando una versión está casi terminada y necesita algunos ajustes o correcciones antes de publicarse.

- hotfix: Se utiliza para solucionar errores importantes que aparecen en una versión que ya fue publicada.

En general, GitFlow permite organizar mejor el desarrollo de un proyecto, ya que cada rama tiene una función y ayuda a mantener separados los cambios nuevos de las versiones estables.