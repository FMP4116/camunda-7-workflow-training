# Monitorización del motor de procesos

## 🎯 Objetivo

Aprender a **monitorizar la actividad del motor Camunda** utilizando Cockpit y analizar el estado de ejecución del sistema.

---

## 🧠 Contexto

En sistemas de workflow en producción es importante monitorizar:

```id="d1e3q4"
procesos ejecutándose
instancias activas
jobs pendientes
errores o incidentes
```

Camunda proporciona herramientas integradas para observar el estado del motor.

La principal herramienta es:

```id="j4v7n6"
Cockpit
```

---

# Abrir Camunda Cockpit

Arrancar la aplicación si no está en ejecución:

```bash id="c3m5z2"
cd workflow-app
mvn spring-boot:run
```

Abrir el navegador:

```id="x7n2w4"
http://localhost:8081/camunda
```

Entrar en la aplicación **Cockpit**.

---

# Ver procesos desplegados

Ir a la sección:

```id="s2k9v5"
Processes
```

Aquí se muestran todos los procesos desplegados en el motor.

Seleccionar el proceso:

```id="a9f1d0"
approval-process
```

---

# Analizar estadísticas del proceso

En la pantalla del proceso se pueden observar métricas como:

```id="v4h0r3"
instancias activas
instancias completadas
instancias fallidas
```

Estas estadísticas permiten conocer el comportamiento del proceso.

---

# Ver jobs del motor

Ir a la sección:

```id="z6w3n8"
Jobs
```

Aquí se pueden ver tareas internas del motor como:

```id="y7c8x5"
jobs asíncronos
temporizadores
reintentos
```

Los jobs representan trabajo pendiente dentro del motor.

---

# Analizar incidentes

Si ocurre un error en el sistema, aparecerá un indicador en Cockpit.

Ir a:

```id="w1t2r7"
Incidents
```

Aquí se puede observar:

```id="t5p9m6"
tipo de incidente
mensaje de error
instancia afectada
```

Esto permite detectar problemas en el sistema.

---

# Explorar instancias activas

Ir a:

```id="r8b2j1"
Process Instances
```

Seleccionar una instancia.

Cockpit mostrará:

```id="p4k7s6"
estado actual
actividades ejecutadas
variables
```

Esto permite analizar la ejecución del proceso en tiempo real.

---

# Qué se ha aprendido

La monitorización permite:

```id="f6z3k9"
identificar procesos activos
detectar errores
analizar comportamiento del sistema
supervisar la ejecución del workflow
```

Estas herramientas son fundamentales para operar el motor en producción.

---

# Comprobación

El ejercicio se considera completado cuando:

* se accede a Cockpit
* se visualizan estadísticas del proceso
* se inspeccionan jobs del motor
* se revisan incidentes o instancias activas.
