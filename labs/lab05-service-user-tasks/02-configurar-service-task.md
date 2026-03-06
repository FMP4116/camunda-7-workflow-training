# Configurar la Service Task

## 🎯 Objetivo

Configurar la **Service Task** del modelo BPMN para que ejecute la clase Java creada en el ejercicio anterior.

---

## 🧠 Contexto

En el ejercicio anterior se creó una clase:

```id="5tdh7a"
ValidarSolicitudDelegate
```

Esta clase implementa:

```id="b98sna"
JavaDelegate
```

Ahora es necesario indicar en el modelo BPMN que la **Service Task** debe ejecutar esa clase cuando el proceso llegue a ese punto.

Esto se hace configurando el atributo:

```id="p6k3sh"
Delegate Expression
```

---

# Abrir el modelo BPMN

Abrir el archivo:

```
model/approval-process.bpmn
```

Editar el modelo usando **Camunda Modeler**.

---

# Seleccionar la Service Task

Seleccionar la tarea llamada:

```
Validar solicitud
```

En el panel derecho aparecerán las propiedades del elemento.

---

# Configurar el tipo de implementación

En la sección **Implementation** seleccionar:

```
Delegate Expression
```

---

# Configurar la expresión del delegate

Introducir la siguiente expresión:

```
${validarSolicitudDelegate}
```

Esto indica al motor Camunda que debe ejecutar el **bean Spring** correspondiente a esa clase.

El nombre del bean se genera automáticamente a partir del nombre de la clase:

```
ValidarSolicitudDelegate
```

↓

```
validarSolicitudDelegate
```

---

# Guardar el modelo

Guardar los cambios en el archivo:

```
model/approval-process.bpmn
```

---

# Copiar el modelo al backend

Copiar el modelo al directorio donde Camunda despliega procesos:

```bash
cp model/approval-process.bpmn backend/src/main/resources/processes/
```

---

# Ejecutar la aplicación

Ir al directorio del backend:

```bash
cd backend
```

Ejecutar la aplicación:

```bash
mvn spring-boot:run
```

---

# Verificar la ejecución del delegate

Cuando el proceso se ejecute, el motor llamará al método:

```java
execute()
```

de la clase:

```
ValidarSolicitudDelegate
```

En la consola debería aparecer el mensaje:

```
Ejecutando validación automática de la solicitud
```

---

# Qué ha ocurrido

El flujo ahora funciona de la siguiente forma:

```
Inicio
   │
   ▼
Service Task (Validar solicitud)
   │
   ▼
Ejecuta ValidarSolicitudDelegate
   │
   ▼
Aprobar solicitud
   │
   ▼
Fin
```

---

# Comprobación

El ejercicio se considera completado cuando:

* la Service Task tiene configurado un **Delegate Expression**
* el modelo BPMN se actualiza en `resources/processes`
* al ejecutar el proceso se llama a `ValidarSolicitudDelegate`.
