1: 
Git es un sistema de control de versiones distribuido diseñado para registrar los cambios en los archivos de un proyecto a lo largo del tiempo.

En el desarrollo de software, resuelve problemas fundamentales relacionados con la coordinación y el mantenimiento del código:

Trabajo colaborativo simultáneo: Permite que múltiples desarrolladores trabajen en el mismo proyecto o incluso en el mismo archivo al mismo tiempo. Git gestiona la fusión de estas aportaciones y, si dos personas modifican la misma línea, alerta sobre el conflicto para que se resuelva manualmente, evitando que el trabajo de uno sobrescriba el del otro.

Trazabilidad y auditoría: Mantiene un historial exacto de cada modificación. Permite saber quién cambió el código, qué líneas específicas se alteraron, cuándo se hizo y cuál fue el motivo (a través del mensaje del commit).

Experimentación aislada (Ramas): Mediante el uso de branches, permite crear copias de trabajo independientes. Se puede desarrollar una nueva funcionalidad o corregir un error crítico sin riesgo de romper el código de la rama principal (producción). Una vez que el código nuevo es estable, se integra.

Recuperación ante errores: Si un nuevo despliegue falla o se introduce un bug, Git permite revertir el proyecto a un estado anterior completamente funcional de manera rápida y segura.

En la práctica, elimina la gestión manual de archivos (como proyecto_v1, proyecto_final, proyecto_final_ahora_si) y estructura el caos del trabajo en equipo en un flujo organizado.