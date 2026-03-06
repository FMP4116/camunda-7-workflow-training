# Exportar modelo BPMN

## 🎯 Objetivo

Guardar y verificar el modelo BPMN creado en el laboratorio anterior para que pueda ser utilizado posteriormente por el motor Camunda.

---

## 🧠 Contexto

Los procesos BPMN se almacenan en archivos con extensión:

```
.bpmn
```

Estos archivos contienen una representación **XML del proceso**.

El motor Camunda utilizará este archivo para:

* desplegar el proceso
* ejecutar el workflow
* gestionar el estado del proceso

Por lo tanto es importante que el modelo esté **guardado correctamente dentro del repositorio**.

---

# Guardar modelo usando Camunda Modeler

Si el proceso se creó usando **Camunda Modeler**:

1. Ir al menú

```
File → Save
```

2. Seleccionar el directorio del proyecto:

```
model/
```

3. Guardar el archivo con el nombre:

```
primer-proceso.bpmn
```

---

# Guardar modelo usando VS Code

Si el proceso se editó desde **VS Code**:

1. Abrir el archivo

```
model/primer-proceso.bpmn
```

2. Guardar el archivo usando:

```
CTRL + S
```

El archivo quedará almacenado dentro del repositorio.

---

# Verificar que el archivo existe

Abrir una terminal y ejecutar:

```bash
ls model
```

Debería aparecer el archivo:

```
primer-proceso.bpmn
```

---

# Verificar contenido del archivo

Los archivos BPMN son **XML**, por lo que se pueden abrir en cualquier editor.

Abrir el archivo:

```
model/primer-proceso.bpmn
```

Debería comenzar con algo similar a:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<bpmn:definitions ...
```

Esto indica que el modelo BPMN se ha guardado correctamente.

---

# Resultado esperado

El directorio `model` debería contener ahora el proceso creado:

```
model/
└── primer-proceso.bpmn
```

Este modelo será utilizado en los siguientes laboratorios para **desplegar y ejecutar procesos en Camunda**.
