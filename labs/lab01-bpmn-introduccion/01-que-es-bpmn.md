# Qué es BPMN

## 🎯 Objetivo

Comprender qué es **BPMN** observando y analizando un proceso representado mediante un diagrama.

---

## 🧠 Contexto

Antes de crear nuestros propios procesos es útil **ver un proceso BPMN real**.

En este paso vamos a:

1. abrir un modelo BPMN existente
2. observar sus elementos
3. identificar las partes principales de un proceso

---

## 📥 Abrir el modelo de ejemplo

Ir al directorio:

```
model
```

Abrir el archivo BPMN disponible en ese directorio.

El archivo tendrá extensión:

```
.bpmn
```

Si el editor BPMN está instalado, VS Code mostrará el **diagrama del proceso**.

---

## 🔎 Identificar los elementos del proceso

Observar el diagrama y localizar los siguientes elementos:

### Evento de inicio

Representa el **punto donde comienza el proceso**.

En BPMN se representa con un **círculo verde**.

---

### Actividad

Representa una **acción dentro del proceso**.

Se representa con un **rectángulo con bordes redondeados**.

Las actividades pueden representar:

* trabajo realizado por personas
* tareas automáticas
* integraciones con sistemas

---

### Flujo de secuencia

Representa el **orden en el que se ejecutan las actividades**.

Se representa mediante **flechas**.

---

### Evento de fin

Representa el **final del proceso**.

Se representa con un **círculo rojo**.

---

## ✏️ Analizar el flujo del proceso

Intentar responder a las siguientes preguntas observando el diagrama:

* ¿Dónde empieza el proceso?
* ¿Qué actividades se ejecutan?
* ¿En qué orden se ejecutan?
* ¿Dónde termina el proceso?

---

## 📌 Conclusión

Un modelo BPMN describe **cómo fluye un proceso de negocio** desde que empieza hasta que finaliza.

El motor de procesos utilizará este modelo para **ejecutar el workflow paso a paso**.

En el siguiente paso crearemos **nuestro primer proceso BPMN**.
