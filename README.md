# Guía de Actividad: Dominando Git, GitHub y GitFlow

**Modalidad:** Individual.

Esta actividad está dividida en dos grandes secciones: primero, una investigación teórica que deberán entregar a mi repositorio mediante un flujo de *Pull Requests*; y segundo, una simulación práctica del flujo de trabajo **GitFlow** que realizarán en sus propias cuentas.

---

## Parte 1: Contextualización e Investigación

Antes de escribir comandos, es crucial entender las herramientas. Deberán investigar los siguientes puntos. Las respuestas formarán parte de su entregable.

1. **¿Qué es Git y qué problema resuelve en el desarrollo de software?**
2. **Diferencias clave entre Git y GitHub.** (Expliquen por qué no son lo mismo).
3. **¿Qué es una nube de repositorios?** Expliquen este concepto y mencionen al menos tres alternativas diferentes en el mercado (por ejemplo, además de GitHub, ¿qué otras plataformas existen?).
4. **Glosario básico:** Definan con sus propias palabras, de forma clara y **agregando un ejemplo práctico para cada uno**, los siguientes conceptos fundamentales de Git:
   * *Commit*
   * *Branch* (Rama)
   * *Merge* (Fusión)
   * *Pull* y *Push*
   * *Pull Request (PR)*
   * *Clone* (Clonar)
   * *Upstream* (y su diferencia con *Origin*)
5. **La importancia de las ramas (Branches):** ¿Por qué se deben crear ramas en un proyecto de software? Expliquen para qué sirven y qué ventajas ofrecen tanto en el trabajo individual como en equipo.
6. **¿Qué es GitFlow?** Expliquen brevemente la estructura de sus ramas principales (`master`, `develop`, `feature`, `release`, `hotfix`).

---

## Parte 2: Entrega de la Investigación (Flujo Fork y Pull Request)

He creado un repositorio base para esta clase. Este repositorio ya cuenta con las ramas `master` y `develop`. Para entregar su investigación, deberán seguir estrictamente el siguiente paso a paso, diseñado para que no necesiten ayuda adicional si leen con atención.

### Fase 1: Hacer Fork del repositorio
Un *Fork* es una copia exacta de mi repositorio original, pero guardada en su cuenta personal de GitHub.
1. Entren al enlace del repositorio que les he compartido.
2. En la esquina superior derecha de la página de GitHub, hagan clic en el botón que dice **"Fork"**.
3. Seleccionen su cuenta de GitHub personal como destino.
4. **¡Muy importante!** Desmarquen la casilla inferior que dice **"Copy the `master` branch only"** (Copiar solo la rama master). Necesitamos que se copien todas las ramas (`master` y `develop`) a su fork.
5. Hagan clic en **"Create fork"**. Ahora tienen su propia copia del repositorio en su cuenta.

### Fase 2: Clonar el repositorio y crear una rama desde Develop
Ahora deben llevar ese repositorio de la nube a su computadora local y preparar el entorno aislando su trabajo.
1. En su repositorio *forkeado*, hagan clic en el botón verde **"<> Code"** y copien la URL (HTTPS o SSH).
2. Abran su terminal o línea de comandos.
3. Ejecuten: `git clone <URL_QUE_COPIARON>`
4. Entren a la carpeta del proyecto: `cd <nombre-del-repo>`
5. **Posicionarse en Develop:** Antes de crear cualquier rama nueva, deben asegurarse de que la base sea la rama de desarrollo y no la principal. Ejecuten: 
   `git checkout develop`
6. **Crear la rama de consulta:** Ahora crearán la rama donde harán su trabajo. El nombre debe ser exacto. Ejecuten: 
   `git checkout -b feature/consulta`
7. Abran la carpeta en su editor de código (por ejemplo, ejecutando `code .` para VS Code).

### Fase 3: Creación del archivo de entrega
1. Asegurándose de estar en la rama `feature/consulta`, creen un archivo Markdown (`.md`).
2. El nombre del archivo **debe** seguir exactamente esta estructura: `CC-Nombre.md` (Por ejemplo: `10203040-AnaGomez.md`).
3. En este archivo, redactarán las respuestas de la investigación de la **Parte 1**.

### Fase 4: Un Commit por cada punto de consulta (¡Importante!)
Para demostrar el control de versiones, **no pueden subir todo de una sola vez**. Deben hacer un *commit* separado por cada punto que respondan.

1. Respondan el **Punto 1** en su archivo.
   * Guarden el archivo y ejecuten: `git add .`
   * Ejecuten: `git commit -m "docs: agregar definicion y proposito de Git"`
2. Respondan el **Punto 2** en su archivo.
   * Guarden el archivo y ejecuten: `git add .`
   * Ejecuten: `git commit -m "docs: explicar diferencias entre git y github"`
3. Repitan este proceso (guardar, `add`, `commit`) para los **Puntos 3, 4, 5 y 6**. Asegúrense de usar mensajes de commit descriptivos para cada uno.
4. Una vez tengan todos los commits listos, suban su nueva rama a su repositorio (su fork) en GitHub: 
   `git push origin feature/consulta`

### Fase 5: El flujo de entrega (Doble Pull Request)
Para respetar la filosofía de GitFlow, la entrega se hará en dos pasos. Primero integrarán sus cambios en su propio entorno, y luego me enviarán el resultado. Lean detenidamente.

**Paso 1: Pull Request interno (De su feature a su develop)**
1. Vayan a la página de GitHub de su repositorio *forkeado*.
2. Creen un nuevo **Pull Request**.
3. En la configuración de ramas (los menús desplegables), asegúrense de que:
   * **Base repository:** Sea SU propio repositorio (su fork).
   * **Base:** `develop` (la rama que recibirá los cambios).
   * **Compare:** `feature/consulta` (la rama que tiene sus respuestas).
4. Creen el Pull Request y, una vez creado, hagan clic en **"Merge pull request"** y luego en **"Confirm merge"**. Con esto, su rama `develop` ya contiene su tarea.

**Paso 2: Pull Request externo (De su develop a mi develop)**
1. Vuelvan a la pestaña de "Pull requests" en su repositorio *forkeado* y creen uno nuevo.
2. Esta vez, la configuración de ramas debe ser la siguiente:
   * **Base repository:** MI repositorio original (el del profesor).
   * **Base:** `develop` (mi rama de desarrollo).
   * **Head repository:** SU repositorio (su fork).
   * **Compare:** `develop` (su rama de desarrollo, que ahora tiene la tarea integrada).
3. Pónganle un título claro a su PR (Ej: *Entrega Investigación - Su Nombre*).
4. Hagan clic en **"Create pull request"**. ¡Listo! Su tarea ha sido enviada formalmente a mi repositorio.

---

## Parte 3: Simulación Individual de GitFlow

Ahora que entienden los conceptos y ya interactuaron con el repositorio principal, van a simular el ciclo de vida de **GitFlow** para un lanzamiento (Release) dentro de su propio repositorio.

### Paso a Paso del Flujo:

1. **Posicionarse y actualizar Develop:** 
   * En su terminal, regresen a la rama de desarrollo: `git checkout develop`
   * Traigan los cambios que acaban de fusionar en GitHub (el Paso 1 de la Fase 5): `git pull origin develop`
2. **Crear un nuevo Feature:**
   * Creen otra rama feature: `git checkout -b feature/simulacion-practica`
   * Creen un archivo llamado `practica.txt`, escriban cualquier texto confirmando que llegaron a este punto, guárdenlo.
   * Hagan el ciclo de guardado: `git add .`, `git commit -m "feat: agregar archivo de practica"`, y finalmente `git push origin feature/simulacion-practica`.
3. **Integrar el Feature a Develop:**
   * Vayan a su GitHub (en su fork) y creen un Pull Request desde su rama `feature/simulacion-practica` hacia su propia rama `develop`.
   * Aprueben y hagan el *Merge* de ese Pull Request.
4. **Preparar el Release:**
   * Vuelvan a su terminal y actualicen su develop local: `git checkout develop` y luego `git pull origin develop`.
   * Creen una rama de lanzamiento: `git checkout -b release/v1.0`
   * Creen un archivo `changelog.md` detallando que se agregó la práctica.
   * Hagan `add`, `commit` y `push` de esta rama `release/v1.0`.
5. **Paso a Producción (Master):**
   * En GitHub, abran un PR desde su rama `release/v1.0` hacia su rama `master`. 
   * Hagan el *Merge*. 
   * En un entorno real, también se haría un PR de retorno hacia `develop` por si hubo cambios de última hora en el release, pero para esta simulación, con llegar a `master` habrán completado el ciclo.

---
**¡Mucho éxito dominando las ramas y los flujos de trabajo!**