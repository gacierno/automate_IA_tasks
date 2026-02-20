# automate_IA_tasks
A way to automate task completion without Assistants, just an agent with a cheap model
---
V3: Added a new rule file to enforce a pre-execution protocol to prevent undesired code generation and ambiguous intent.
---

Cómo decidir el TYPE correctamente

No preguntes:

¿Qué tipo es?

Preguntate:

¿Cuánto daño puede causar si está mal?

🟢 DESIGN

Cuando:

Hay ambigüedad.

Querés explorar.

No querés tocar código.

No hay contrato cerrado.

Riesgo casi cero.

🟢 TEST_ONLY

Cuando:

Querés formalizar comportamiento.

Estás afinando reglas.

No querés ejecución todavía.

Riesgo bajo (solo contrato).

🟡 REFACTOR

Cuando:

No cambia comportamiento externo.

Solo estructura interna.

Tests existentes protegen.

Riesgo medio bajo.

🟡 IMPLEMENTATION

Cuando:

El contrato ya está claro.

El comportamiento está definido por tests.

El alcance está acotado.

Riesgo medio.

🔴 SAFE_AUTONOMOUS

Cuando:

Tarea pequeña.

Criterio de DONE 100% verificable por tests.

Sin impacto arquitectónico.

Sin integraciones críticas.

Sin reglas de negocio delicadas.

Riesgo controlado pero ejecución autónoma.
