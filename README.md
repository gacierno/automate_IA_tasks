# automate_IA_tasks

A way to automate task completion without Assistants, just an agent with a cheap model

---

## Lo que estamos haciendo

### Arquitectura.

Un sistema con:
- 📋 Fuente de verdad → Task Manager
- 🏷 TYPE → Permiso de ejecución
- 🔁 Columnas → Estados del workflow
- 👤 Humano → Controlador de transición crítica
- 🤖 Agente → Worker disciplinado


## Ciclo de Vida (esperado)

### Columnas:
- To Do
- In Progress (implícito mientras ejecuta)
- To Review
- Done

### Reglas

El agente toma tareas en To Do.
Ejecuta según TYPE.
Llega hasta el límite permitido por el TYPE.
Mueve la tarea a To Review.

### El humano decide entre:

✅ Pasar a Done
🔁 Cambiar TYPE y volver a To Do
❓ Resolver ambigüedad y volver a To Do

