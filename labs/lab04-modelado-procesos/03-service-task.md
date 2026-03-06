# Añadir una Service Task

## 🎯 Objetivo

Modificar el modelo BPMN para añadir una **Service Task**, que representa una tarea ejecutada automáticamente por el sistema.

---

## 🧠 Contexto

En BPMN una **Service Task** representa una actividad que realiza el sistema sin intervención humana.

Este tipo de tarea suele utilizarse para:

* ejecutar lógica de negocio
* llamar a APIs
* realizar cálculos
* integrar sistemas

En este ejercicio añadiremos una **Service Task** al proceso.

---

# Abrir el modelo del proceso

Abrir el archivo:

```
model/approval-process.bpmn
```

Utilizar **Camunda Modeler** para editar el diagrama.

---

# Insertar una Service Task

Actualmente el proceso tiene este flujo:

```
Inicio → Fin
```

Modificar el proceso para incluir una tarea intermedia.

Seleccionar el elemento:

```
Task
```

Arrastrarlo entre el evento de inicio y el evento de fin.

---

# Convertir la tarea en Service Task

Seleccionar la tarea creada.

En el menú contextual elegir:

```
Service Task
```

Esto indica que la tarea será ejecutada automáticamente por el sistema.

---

# Renombrar la tarea

Asignar el siguiente nombre a la tarea:

```
Validar solicitud
```

---

# Conectar el flujo del proceso

Asegurarse de que el flujo queda de la siguiente forma:

```
Inicio → Validar solicitud → Fin
```

---

# Guardar el modelo

Guardar el archivo:

```
model/approval-process.bpmn
```

---

# Verificar el modelo

El diagrama BPMN debería contener:

* un evento de inicio
* una Service Task
* un evento de fin

Representando el flujo:

```
Inicio
   │
   ▼
Validar solicitud
   │
   ▼
Fin
```

---

# Qué significa esta tarea

La **Service Task** representa una actividad automática.

En laboratorios posteriores se implementará la lógica de esta tarea mediante **código Java**.

---

# Comprobación

El ejercicio se considera completado cuando:

* el modelo contiene una **Service Task**
* la tarea se llama **Validar solicitud**
* el flujo del proceso conecta inicio, tarea y fin
* el archivo BPMN se guarda correctamente.
