# Introducción a DMN

## 🎯 Objetivo

Conocer **DMN (Decision Model and Notation)** y su relación con BPMN: qué son las tablas de decisión y cómo se usan desde procesos en Camunda.

---

## 🧠 Contexto

**DMN** es un estándar para modelar y ejecutar **decisiones de negocio**.

Mientras BPMN describe *flujos de trabajo*, DMN describe *reglas de decisión* en tablas:

* **Input**: variables de entrada (ej. importe, antigüedad).
* **Output**: resultado de la decisión (ej. nivel de aprobación, sí/no).
* **Reglas**: filas que combinan condiciones y asignan el resultado.

En Camunda, un proceso BPMN puede invocar una decisión DMN mediante una **Business Rule Task** o desde código (DecisionService). El motor evalúa la tabla y devuelve el resultado; el proceso usa ese resultado para seguir el flujo.

---

## 📋 Elementos básicos de DMN

Una definición DMN (archivo `.dmn`) contiene:

* **Decision**: nodo que representa la decisión (nombre, expresión o tabla).
* **Input Data**: datos de entrada usados en las condiciones.
* **Decision Table**: tabla con columnas de entrada, salida y filas de reglas.

Las reglas se evalúan en orden; la primera cuya condición se cumple determina la salida.

---

## 🔗 Uso desde BPMN

En un proceso BPMN (en **Camunda Modeler**):

1. En la **paleta de la izquierda** busca **Business Rule Task** (suele estar en el grupo de tareas) y arrástrala al flujo donde quieras que se ejecute la decisión.
2. **Selecciona** esa tarea y en el **panel de propiedades a la derecha** busca la sección donde se referencia la decisión (por ejemplo "Decision" o "Called decision"); ahí pones el **key** de la decisión (el id del nodo de decisión en el archivo .dmn).
3. El motor ejecutará esa decisión con las variables del proceso y guardará el resultado en una variable que tú configuras en las propiedades.

Así la lógica de decisión (umbrales, categorías, aprobaciones) queda en tablas DMN en lugar de repartida en código o expresiones en el diagrama.

---

## 📌 Práctica recomendada

1. **Crear el .dmn:** Abre **Camunda Modeler**, menú **File** → **New File** → **DMN Diagram**. Se abrirá un canvas para DMN (similar al BPMN pero para decisiones). Crea una decisión simple (por ejemplo "nivel de aprobación" según la variable `importe`); el editor DMN tiene su propia paleta y nodos (Decision, Input Data, Decision Table). Si no has usado antes el editor DMN, en labs posteriores se verá con más detalle; por ahora guarda el archivo en **model/** (por ejemplo `model/nivel-aprobacion.dmn`). Si usas VS Code con extensión DMN, también puedes crear/editar el .dmn ahí.
2. **Enlazarlo al proceso:** Abre en Camunda Modeler el **mismo proceso BPMN que uses en este lab** (por ejemplo **model/primer-proceso.bpmn** o **model/approval-process.bpmn**, según lo que tengas). Añade una **Business Rule Task** desde la paleta (como en el apartado anterior), y en sus propiedades indica el key de la decisión que acabas de crear. Usa la variable resultante en un gateway o en una tarea posterior.

En laboratorios posteriores verás la configuración concreta de la Business Rule Task y el binding de variables.

---

## 📌 Conclusión

DMN complementa a BPMN centralizando decisiones en tablas ejecutables; Camunda ejecuta tanto el proceso como las decisiones y los integra mediante Business Rule Task o API.
