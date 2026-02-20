# AI Autonomy Rules v2.0

Estas reglas definen el comportamiento esperado del agente cuando trabaja de forma semi-autónoma o autónoma.

---

## 1. Principios Generales

- Mantener convenciones Rails y estilo consistente.
- No introducir cambios fuera del alcance explícito de la tarea.
- No realizar mejoras no solicitadas.
- Minimizar efectos colaterales.

---

## 2. Uso del Task Manager

Siempre que el usuario solicite tareas:

- Consultar el tareas vía MCP
- Estados válidos: TODO, IN_PROGRESS, DONE.
- Prioridades: URGENTE, ALTA, MEDIA, BAJA.

Nunca asumir tareas sin consultarlas primero.

---

## 3. Validación de Tarea Antes de Ejecutar

Antes de comenzar cualquier implementación:

Verificar que la tarea tenga:

- Objetivo claro y verificable.
- Estado actual suficiente para entender el contexto.
- Subtareas concretas.
- Criterio de DONE implícito o explícito.

Si existe ambigüedad relevante:
→ Detener ejecución y solicitar aclaraciones.

---

## 4. Protocolo Test-First

Para tareas de desarrollo:

1. Generar o validar tests que cubran el Objetivo.
2. Los tests definen el contrato.
3. No modificar tests existentes salvo que la tarea lo indique explícitamente.
4. El criterio de DONE es que:
   - Todos los tests existentes pasen.
   - Los nuevos tests pasen.

Si un test es débil o ambiguo:
→ Reportar antes de implementar.

---

## 5. Alcance de Modificaciones

- Modificar únicamente archivos relacionados con la tarea.
- No refactorizar código no relacionado.
- No cambiar contratos externos.
- No alterar tests existentes sin autorización explícita.

---

## 6. Iteración Controlada

Si la implementación falla:

- Intentar hasta 3 iteraciones razonadas.
- En cada iteración:
  - Analizar causa.
  - Ajustar solo lo necesario.
- Si después de 3 intentos no se resuelve:
  → Detener y marcar como NEEDS_REVIEW con explicación técnica.

No entrar en loops infinitos.

---

## 7. Clasificación de Tareas (si se incluye TYPE)

Tipos posibles:

- TEST_ONLY
- IMPLEMENTATION
- REFACTOR
- DESIGN
- SAFE_AUTONOMOUS

Reglas:

- TEST_ONLY → solo modificar archivos de test.
- IMPLEMENTATION → no modificar tests.
- SAFE_AUTONOMOUS → puede ejecutarse sin confirmación humana si el criterio de DONE es verificable automáticamente.
- DESIGN → no modificar código.
- REFACTOR → no cambiar comportamiento externo.

---

## 8. Criterios para Detener Autonomía

Solicitar revisión humana si la tarea:

- Implica cambios arquitectónicos amplios.
- Modifica reglas de negocio sensibles.
- Afecta integraciones externas críticas.
- No puede validarse automáticamente con tests.

---

## 9. Finalización de Tarea

Una tarea se marca DONE solo si:

- Todos los tests pasan.
- No se rompieron tests existentes.
- El alcance fue respetado.
- El código cumple convenciones Rails.
