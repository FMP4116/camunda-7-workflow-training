# Lab 01 — Introducción a BPMN

## 🎯 Objetivo

Comprender los conceptos básicos de **BPMN (Business Process Model and Notation)** y crear el **primer proceso ejecutable** que posteriormente será utilizado por el motor Camunda.

En este laboratorio se aprenderá a:

* identificar los elementos básicos de BPMN
* modelar un proceso simple
* exportar el modelo BPMN
* preparar el modelo para ser ejecutado por Camunda

---

# 🧠 Contexto

**BPMN** es un estándar para modelar procesos de negocio.

Permite representar gráficamente:

```
actividades
decisiones
eventos
interacciones humanas
automatizaciones
```

Un proceso BPMN describe **cómo fluye el trabajo dentro de un sistema o una organización**.

Ejemplo simplificado:

```
Inicio
  │
  ▼
Validar solicitud
  │
  ▼
Aprobar solicitud
  │
  ▼
Fin
```

Durante este curso, estos modelos BPMN se ejecutarán dentro del **motor Camunda**.

---

# 🧰 Herramientas utilizadas

Para trabajar con BPMN utilizaremos dos herramientas posibles.

### Opción 1 — Camunda Modeler (recomendado)

Camunda proporciona una herramienta oficial llamada:

```
Camunda Modeler
```

Es una aplicación de escritorio diseñada específicamente para crear modelos BPMN.

Ventajas:

```
editor BPMN completo
validaciones automáticas
soporte completo para Camunda
```

Descargar desde:

```
https://camunda.com/download/modeler/
```

---

### Opción 2 — Extensión BPMN para VS Code

También existe una extensión para VS Code que permite editar modelos BPMN.

Instalar extensión:

```
BPMN Editor
```

Esta opción permite trabajar directamente dentro del repositorio del curso.

---

# 📂 Estructura de modelos del curso

Todos los modelos BPMN del curso se almacenarán en el directorio:

```
model/
```

En este laboratorio se creará el primer archivo BPMN dentro de ese directorio.

---

# 📘 Ejercicios del laboratorio

Este laboratorio contiene los siguientes pasos.

### 01 — Qué es BPMN

Introducción práctica al estándar BPMN y sus conceptos básicos.

Archivo:

```
01-que-es-bpmn.md
```

---

### 02 — Elementos básicos

Identificación de los elementos fundamentales del lenguaje BPMN.

Archivo:

```
02-elementos-basicos.md
```

---

### 03 — Crear primer proceso

Creación del primer modelo BPMN del curso.

Archivo:

```
03-crear-primer-proceso.md
```

---

### 04 — Exportar modelo

Preparación del modelo para su posterior ejecución dentro del motor Camunda.

Archivo:

```
04-exportar-modelo.md
```

---

### 05 — Introducción a DMN

Qué es DMN, tablas de decisión y uso desde BPMN (Business Rule Task).

Archivo:

```
05-dmn-introduccion.md
```

---

### 06 — Introducción a CMMN

Qué es CMMN, casos frente a procesos y cuándo usar cada estándar.

Archivo:

```
06-cmmn-introduccion.md
```

---

# 🧪 Resultado esperado

Al finalizar este laboratorio se habrá creado el primer modelo BPMN del curso.

Archivo generado:

```
model/approval-process.bpmn
```

Este modelo representará un flujo básico de aprobación que será utilizado en los siguientes laboratorios.

---

# 🔜 Próximo laboratorio

En el siguiente laboratorio se estudiará la **arquitectura del motor Camunda** y cómo ejecuta los modelos BPMN.
