# Eventos de inicio y fin

## 🎯 Objetivo

Modificar el modelo BPMN para añadir **eventos de inicio y fin**, definiendo claramente dónde comienza y termina el proceso.

---

## 🧠 Contexto

En BPMN todo proceso debe tener al menos:

* un **evento de inicio**
* un **evento de fin**

Estos elementos definen el flujo básico de ejecución del proceso.

El motor Camunda inicia el proceso desde el **Start Event** y lo finaliza cuando alcanza un **End Event**.

---

# Abrir el modelo del proceso

Abrir el archivo creado en el paso anterior.

En Camunda Modeler seleccionar:

```
File → Open File
```

Abrir:

```
model/approval-process.bpmn
```

Se mostrará el diagrama BPMN.

---

# Añadir evento de inicio

En el panel de herramientas de la izquierda seleccionar:

```
Start Event
```

Arrastrar el elemento al diagrama.

Asignar el nombre:

```
Inicio
```

Este evento representa el punto donde el proceso comienza.

---

# Añadir evento de fin

Seleccionar el elemento:

```
End Event
```

Arrastrarlo al diagrama.

Asignar el nombre:

```
Fin
```

Este evento representa el final del proceso.

---

# Conectar los eventos

Crear un flujo entre los eventos.

Seleccionar el **Start Event** y utilizar la herramienta de conexión.

Conectar:

```
Inicio → Fin
```

Esto crea el flujo mínimo de un proceso BPMN.

---

# Guardar el modelo

Guardar los cambios en el archivo:

```
model/approval-process.bpmn
```

---

# Verificar el diagrama

El modelo debería representar un flujo similar a:

```
Inicio → Fin
```

Este es el **proceso BPMN más simple posible**.

---

# Qué ocurre en el motor

Cuando el motor ejecuta este proceso:

1. se inicia la instancia
2. se alcanza el evento de inicio
3. el flujo avanza directamente al evento de fin
4. el proceso termina

---

# Comprobación

El ejercicio se considera completado cuando:

* el modelo contiene un **Start Event**
* el modelo contiene un **End Event**
* ambos elementos están conectados
* el archivo BPMN se guarda correctamente.
