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

Si creaste el proceso en **Camunda Modeler**:

1. En la **parte superior** de la ventana, menú **File**. Haz clic en **File** y luego en **Save** (o **Save As** si es la primera vez que guardas). El menú File sirve para crear, abrir y guardar archivos.
2. Cuando se abra el cuadro de guardar, navega hasta la carpeta **model/** del repositorio (la misma raíz donde están la carpeta **labs** y el **README**).
3. En "Nombre de archivo" (o "File name") escribe: **primer-proceso.bpmn** y confirma. Verás el archivo dentro de `model/`.

---

# Guardar modelo usando VS Code

Si estás editando desde **VS Code**:

1. Abre el archivo **model/primer-proceso.bpmn** en el editor (desde el explorador de archivos a la izquierda, o con Ctrl+P y escribiendo el nombre).
2. Guarda con **Ctrl + S** (o Cmd + S en Mac). Abajo en la barra de estado verás que desaparece el punto del nombre del archivo cuando está guardado. El archivo queda en el repositorio dentro de `model/`.

---

# Verificar que el archivo existe

Abre una terminal (en VS Code: menú **Terminal** → **New Terminal**, o atajo según tu sistema). Asegúrate de estar en la **raíz del repositorio** (la carpeta donde están **labs**, **model** y el **README**). Desde ahí ejecuta:

```bash
ls model
```

Deberías ver en la lista el archivo **primer-proceso.bpmn**. Si no está, vuelve a guardar en Camunda Modeler o en VS Code asegurándote de elegir la carpeta `model/`.

---

# Verificar contenido del archivo

Los archivos BPMN son **XML**, por lo que se pueden abrir en cualquier editor.

En el explorador de archivos de VS Code (izquierda), abre **model/primer-proceso.bpmn** (o usa **Ctrl+P** y escribe `primer-proceso` para abrirlo). Si lo abres en modo texto, debería comenzar con algo similar a:

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
