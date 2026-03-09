# Debug de instancias de proceso

## 🎯 Objetivo

Aprender a **depurar una instancia de proceso** utilizando el código Java y las herramientas del motor Camunda.

---

## 🧠 Contexto

Cuando un proceso BPMN no se comporta como se espera, es necesario **analizar su ejecución paso a paso**.

Las herramientas principales para depurar procesos son:

```id="y6n8m2"
logs de la aplicación
variables del proceso
Cockpit
debugger del IDE
```

En este ejercicio se utilizará el **debugger de Java** para observar la ejecución de un `JavaDelegate`.

---

# Abrir el delegate

Abrir el archivo:

```id="w1k2d9"
workflow-app/src/main/java/com/example/workflow/delegate/ValidarSolicitudDelegate.java
```

Localizar el método:

```id="v4t8p7"
execute(DelegateExecution execution)
```

---

# Añadir un breakpoint

En el IDE (VS Code o IntelliJ) añadir un **breakpoint** en la línea:

```java id="j7p3n5"
Integer importe = (Integer) execution.getVariable("importe");
```

Este breakpoint permitirá detener la ejecución cuando el proceso llegue a esa tarea.

---

# Arrancar la aplicación en modo debug

Ejecutar la aplicación en modo debug.

Si se utiliza Maven:

```bash id="g4e2t1"
mvn spring-boot:run
```

O iniciar la aplicación desde el IDE con el modo **Debug**.

---

# Ejecutar el proceso

Iniciar una nueva instancia del proceso.

Esto puede hacerse desde:

```id="r9m3y2"
Cockpit
Tasklist
API REST
```

Cuando el proceso llegue a la **Service Task**, el debugger detendrá la ejecución.

---

# Inspeccionar variables

En el debugger se podrán observar las variables disponibles en `execution`.

Ejemplo:

```id="c1z9n8"
solicitante
importe
tipoSolicitud
estadoSolicitud
```

Estas variables corresponden a los datos del proceso.

---

# Explorar el contexto de ejecución

Desde el objeto:

```id="m5f4x1"
DelegateExecution
```

se puede acceder a información del proceso como:

```id="k9u8p0"
execution.getProcessInstanceId()
execution.getCurrentActivityId()
execution.getVariables()
```

Esto permite entender en qué punto del proceso se encuentra la ejecución.

---

# Continuar la ejecución

Una vez analizadas las variables, continuar la ejecución del proceso utilizando el botón:

```id="q3k7n2"
Resume / Continue
```

El proceso continuará su flujo normal.

---

# Qué se ha aprendido

El debugger permite:

```id="f7p6a3"
detener la ejecución de una tarea
inspeccionar variables
analizar lógica de negocio
comprender el flujo del proceso
```

Esto facilita detectar errores en la implementación del workflow.

---

# Comprobación

El ejercicio se considera completado cuando:

* se añade un breakpoint en el delegate
* la ejecución del proceso se detiene en el breakpoint
* se inspeccionan las variables del proceso
* el proceso continúa después del debug.
