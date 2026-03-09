# Inspección de instancias del proceso

## 🎯 Objetivo

Aprender a **analizar una instancia de proceso en ejecución** utilizando Camunda Cockpit.

---

## 🧠 Contexto

Una **Process Instance** representa una ejecución concreta de un proceso BPMN.

Cada instancia mantiene:

```id="h8x6q2"
estado del proceso
variables
historial de actividades
jobs del motor
errores o incidentes
```

Cockpit permite inspeccionar todos estos elementos para entender **qué está ocurriendo dentro del proceso**.

---

# Abrir Camunda Cockpit

Arrancar la aplicación si no está en ejecución:

```bash id="mhtq2u"
cd workflow-app
mvn spring-boot:run
```

Abrir el navegador:

```id="x5ru9a"
http://localhost:8081/camunda
```

Entrar en **Cockpit**.

---

# Localizar el proceso

Ir a:

```id="6qrsrk"
Processes
```

Seleccionar:

```id="b5k0tn"
approval-process
```

---

# Abrir una instancia del proceso

En la parte inferior aparece la sección:

```id="5b5i0b"
Process Instances
```

Seleccionar una de las instancias.

---

# Analizar el diagrama de ejecución

Cockpit mostrará el **modelo BPMN interactivo**.

En el diagrama se puede observar:

```id="8lgp1s"
actividades completadas
actividad actual del proceso
flujo seguido por la instancia
```

Las actividades activas aparecerán resaltadas.

Esto permite entender **en qué punto del proceso se encuentra la ejecución**.

---

# Explorar las variables

Abrir la pestaña:

```id="i6p4hh"
Variables
```

Aquí se pueden observar las variables del proceso.

Ejemplo:

```id="p1xv9q"
solicitante
importe
tipoSolicitud
estadoSolicitud
aprobada
```

Estas variables contienen los datos utilizados por el workflow.

---

# Ver el historial de ejecución

Abrir la pestaña:

```id="j9n0we"
History
```

Aquí se puede ver:

```id="w99z9r"
actividades ejecutadas
duración de cada tarea
orden de ejecución
```

Esto permite analizar cómo se ha ejecutado el proceso.

---

# Ver los jobs del motor

Abrir la pestaña:

```id="s3a5o6"
Jobs
```

Aquí se muestran:

```id="jdxz6c"
temporizadores
reintentos
jobs asíncronos
```

Esto permite identificar tareas pendientes del motor.

---

# Ver incidentes

Si ocurre un error, Cockpit mostrará un indicador en el diagrama.

En la sección:

```id="2oypt9"
Incidents
```

se puede ver:

```id="h1q91s"
mensaje del error
job asociado
estado del incidente
```

---

# Qué se ha aprendido

Analizando una instancia en Cockpit se puede conocer:

```id="vnyh9f"
dónde está el proceso
qué variables tiene
qué actividades se han ejecutado
si existen errores
```

Esto permite diagnosticar problemas y comprender el comportamiento del workflow.

---

# Comprobación

El ejercicio se considera completado cuando:

* se abre una instancia del proceso en Cockpit
* se observa el flujo seguido por el proceso
* se inspeccionan las variables
* se revisa el historial de ejecución.
