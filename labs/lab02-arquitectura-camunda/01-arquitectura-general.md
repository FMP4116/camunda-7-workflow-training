# Arquitectura general de Camunda

## 🎯 Objetivo

Comprender la **arquitectura general** de Camunda y los componentes que forman el sistema. En el **lab03** añadirás el motor al proyecto y validarás cada dependencia; al arrancar verás entonces estos componentes en los logs.

---

## 🧠 Contexto

Camunda es un **motor de ejecución de procesos**.

Su función es:

* ejecutar procesos BPMN
* gestionar el estado del workflow
* coordinar tareas humanas y automáticas
* persistir la información del proceso

Para entender cómo funciona Camunda es importante conocer los **componentes principales del sistema**.

---

## 📊 Arquitectura básica

Cuando el motor esté instalado (lab03), la arquitectura será:

```
BPMN Model
      │
      ▼
Spring Boot Application
      │
      ▼
Camunda Process Engine
      │
      ▼
Database
```

---

## 🔎 Componentes que verás al arrancar (después del lab03)

Cuando en el **lab03** añadas la dependencia de Camunda y arranques la aplicación, en los logs aparecerá algo como:

* **Process Engine** — `ENGINE-00001 Process Engine default created`: el motor se ha inicializado.
* **Base de datos** — Camunda usa una BD (en el curso, H2) para estado, tareas e historial.
* **Servidor web** — Spring Boot arranca el servidor (puerto 8080); las consolas de Camunda (Cockpit, Tasklist) se sirven ahí.

Puedes **validarlo en la práctica** arrancando la aplicación (paso 06 del lab00 o en lab03): en los logs deberías ver el mensaje del Process Engine.

---

## ✅ Comprobación

El ejercicio se considera completado cuando:

* se comprende la arquitectura: BPMN → Spring Boot → Process Engine → Base de datos
* se sabe que el motor se añadirá en lab03 y allí se validará cada dependencia.

---

## 📚 Referencia

[Arquitectura de Camunda – referencia](../../docs/referencia/arquitectura-camunda.md)
