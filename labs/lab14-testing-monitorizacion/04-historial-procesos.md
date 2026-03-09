# Historial de procesos

## 🎯 Objetivo

Aprender a consultar el **historial de ejecución de procesos** y analizar cómo se ha ejecutado una instancia BPMN.

---

## 🧠 Contexto

El motor Camunda registra información histórica sobre la ejecución de los procesos.

Este historial permite analizar:

```id="m4z7x1"
qué actividades se ejecutaron
cuánto tiempo duró cada tarea
qué variables se utilizaron
cuándo empezó y terminó el proceso
```

Esta información es útil para:

```id="p9h2q5"
auditoría
análisis de rendimiento
debug de procesos
monitorización operativa
```

---

# Ejecutar varias instancias del proceso

Arrancar la aplicación si no está en ejecución:

```bash id="c3v8s1"
cd workflow-app
mvn spring-boot:run
```

Iniciar varias instancias del proceso `approval-process`.

Esto puede hacerse desde:

```id="q1j7w6"
Tasklist
API REST
Cockpit
```

Cada ejecución generará información histórica.

---

# Abrir Camunda Cockpit

Abrir el navegador:

```id="g5n4e2"
http://localhost:8081/camunda
```

Entrar en **Cockpit**.

---

# Abrir el proceso

Ir a:

```id="x2t9r8"
Processes
```

Seleccionar:

```id="k3h7f6"
approval-process
```

---

# Acceder al historial

En la parte superior seleccionar la pestaña:

```id="a8c4j0"
History
```

Aquí se pueden observar las instancias finalizadas del proceso.

---

# Inspeccionar una instancia

Seleccionar una instancia completada.

Cockpit mostrará el **diagrama del proceso con el flujo ejecutado**.

Se podrán ver:

```id="r5y2n3"
actividades ejecutadas
orden de ejecución
duración de cada actividad
```

---

# Explorar variables históricas

Abrir la sección:

```id="v7u6p1"
Variables
```

Aquí se muestran las variables utilizadas durante la ejecución del proceso.

Ejemplo:

```id="w9b8k4"
solicitante
importe
tipoSolicitud
estadoSolicitud
```

Estas variables permiten entender qué decisiones tomó el proceso.

---

# Analizar tiempos de ejecución

En la sección de actividades se pueden observar datos como:

```id="d3m7q9"
hora de inicio
hora de finalización
duración de la actividad
```

Esto permite analizar el rendimiento del workflow.

---

# Qué ocurre internamente

Durante la ejecución del proceso, el motor registra eventos históricos:

```id="y4n2h8"
inicio de proceso
ejecución de actividades
actualización de variables
fin del proceso
```

Estos eventos se almacenan en las tablas históricas del motor.

---

# Comprobación

El ejercicio se considera completado cuando:

* se ejecutan varias instancias del proceso
* se accede a la pestaña **History**
* se inspecciona una instancia finalizada
* se visualizan actividades y variables históricas.
