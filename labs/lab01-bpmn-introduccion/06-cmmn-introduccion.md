# Introducción a CMMN

## 🎯 Objetivo

Conocer **CMMN (Case Management Model and Notation)** y cuándo usarlo frente a BPMN: casos frente a procesos estructurados.

---

## 🧠 Contexto

**CMMN** es un estándar para modelar **casos** (cases): trabajo donde el flujo no está totalmente prefijado y el usuario o el sistema decide qué hacer a continuación.

Diferencias principales con BPMN:

| BPMN | CMMN |
|------|------|
| Flujo definido (secuencia, gateways) | Plan de etapas; orden y activación más flexibles |
| Proceso = camino predecible | Caso = conjunto de tareas/stages que pueden activarse según contexto |
| Ideal para procesos repetibles | Ideal para expedientes, gestión de incidencias, tramitación adaptable |

En CMMN se modelan **stages**, **tasks** (humanas o automáticas), **milestones** y **sentries** (condiciones para habilitar o completar elementos). Un elemento puede estar disponible (available), habilitado (enabled), activo o completado.

---

## 🔗 Camunda y CMMN

Camunda 7 incluye **motor CMMN**: puedes desplegar archivos `.cmmn` y ejecutar casos desde la misma aplicación donde corre BPMN. Las APIs (CaseService, etc.) permiten iniciar casos, completar tareas de caso y consultar estado.

Si quieres probar un diagrama CMMN en **Camunda Modeler**: menú **File** → **New File** y busca **CMMN Diagram**. Si no aparece esa opción, tu versión del Modeler no incluye editor CMMN; no es necesario para seguir el curso. El foco aquí es BPMN; CMMN se usa cuando el negocio necesita flexibilidad de plan (qué tareas hacer y en qué orden) más que un flujo fijo.

---

## 📌 Conclusión

CMMN cubre escenarios de casos adaptativos; BPMN cubre procesos con flujo claro. Conocer ambos permite elegir el modelo adecuado (proceso vs caso) y aprovechar el motor CMMN de Camunda cuando aplique.
