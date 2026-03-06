# Elementos básicos de BPMN

## 🎯 Objetivo

Identificar los **elementos fundamentales de BPMN** observando y modificando un proceso existente.

---

## 🧠 Contexto

En el paso anterior abrimos un proceso BPMN y observamos su estructura.

BPMN utiliza un conjunto pequeño de elementos para representar la mayoría de procesos:

* eventos
* actividades
* flujos
* decisiones

En este ejercicio vamos a **identificar y modificar algunos de estos elementos** dentro del modelo.

---

## 📍 Abrir el modelo BPMN

Abrir el archivo:

```
model/proceso-ejemplo.bpmn
```

Si el editor BPMN está instalado, se mostrará el diagrama visual del proceso.

---

## 🔎 Identificar los elementos del proceso

Localizar en el diagrama los siguientes elementos.

### Evento de inicio

Representa el punto donde comienza el proceso.

Símbolo:

```
círculo simple
```

En el modelo corresponde al elemento:

```
Inicio del proceso
```

---

### Actividades

Representan acciones dentro del proceso.

Símbolo:

```
rectángulo con bordes redondeados
```

En el modelo aparecen dos actividades:

```
Revisar solicitud
Aprobar solicitud
```

---

### Flujo de secuencia

Representa el orden de ejecución de las actividades.

Símbolo:

```
flecha
```

Las flechas conectan los elementos del proceso.

---

### Evento de fin

Representa el final del proceso.

Símbolo:

```
círculo con borde más grueso
```

En el modelo corresponde al elemento:

```
Fin del proceso
```

---

## ✏️ Modificar el proceso

Modificar el modelo realizando el siguiente cambio.

Cambiar el nombre de la actividad:

```
Revisar solicitud
```

por:

```
Validar solicitud
```

Guardar el archivo después de realizar el cambio.

---

## 🔎 Verificar el cambio

Después de guardar el archivo comprobar que el diagrama muestra el nuevo nombre de la actividad.

El proceso ahora debería verse así:

```
Inicio → Validar solicitud → Aprobar solicitud → Fin
```

---

## ✅ Comprobación

El ejercicio se considera completado cuando:

* se ha abierto el archivo BPMN
* se han identificado los elementos del proceso
* se ha modificado el nombre de una actividad
* el modelo BPMN se ha guardado correctamente.
