# External Tasks

## 🎯 Objetivo

Comprender el patrón **External Task** y configurar una tarea del proceso que será ejecutada por un **worker externo**.

---

## 🧠 Contexto

Hasta ahora las **Service Tasks** se ejecutaban dentro de la propia aplicación mediante `JavaDelegate`.

Sin embargo, en arquitecturas modernas es común que el proceso delegue trabajo a **servicios externos**.

Para esto Camunda utiliza el patrón:

```id="c8q0z7"
External Task
```

El flujo funciona así:

```id="0rxphm"
Proceso BPMN
      │
      ▼
External Task
      │
      ▼
Worker externo solicita trabajo
      │
      ▼
Worker ejecuta tarea
      │
      ▼
Worker notifica finalización
```

Este patrón permite integrar:

```id="m3y1c0"
microservicios
workers en otros lenguajes
procesos distribuidos
sistemas externos
```

---

# Modificar la Service Task

Abrir el modelo BPMN:

```id="1xibp7"
model/approval-process.bpmn
```

Seleccionar la tarea:

```id="7z3l4v"
Validar solicitud
```

---

# Cambiar el tipo de implementación

En el panel de propiedades configurar:

```id="5zt2b5"
Implementation = External
```

Esto indica que la tarea será ejecutada por un worker externo.

---

# Configurar el Topic

Configurar el campo:

```id="fmy7vq"
Topic
```

Valor:

```id="szv1yl"
validar-solicitud
```

Este será el identificador que utilizarán los workers para solicitar trabajo.

---

# Guardar el modelo

Guardar el archivo:

```id="b07x0y"
model/approval-process.bpmn
```

Copiar el modelo a workflow-app:

```bash id="t8v7fl"
cp model/approval-process.bpmn workflow-app/src/main/resources/processes/
```

---

# Qué ocurrirá ahora

Cuando el proceso llegue a la tarea:

```id="b0u5ke"
Validar solicitud
```

Camunda creará una **External Task** en el motor.

El proceso quedará esperando hasta que un worker externo procese la tarea.

---

# Consultar External Tasks mediante REST

Arrancar la aplicación:

```bash id="0ne9o7"
cd workflow-app
mvn spring-boot:run
```

Consultar las tareas externas:

```bash id="u8hny8"
curl http://localhost:8081/engine-rest/external-task
```

La respuesta mostrará tareas pendientes de ejecución.

---

# Qué contiene una External Task

La respuesta incluirá información como:

```id="0sjxgx"
id
topicName
processInstanceId
retries
workerId
```

Estas tareas serán consumidas por workers externos.

---

# Flujo del patrón External Task

```id="b9tqpl"
Proceso BPMN
      │
      ▼
External Task creada
      │
      ▼
Worker solicita tarea
      │
      ▼
Worker ejecuta lógica
      │
      ▼
Worker completa tarea
```

Esto desacopla el motor del código que ejecuta la tarea.

---

# Comprobación

El ejercicio se considera completado cuando:

* la Service Task está configurada como **External**
* el modelo define el topic `validar-solicitud`
* el motor crea una **External Task** cuando se ejecuta el proceso.
