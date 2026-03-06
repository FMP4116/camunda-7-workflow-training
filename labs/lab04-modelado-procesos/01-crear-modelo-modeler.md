# Crear modelo con Camunda Modeler

## 🎯 Objetivo

Crear un nuevo **modelo BPMN** utilizando **Camunda Modeler** y guardarlo dentro del repositorio del proyecto.

---

## 🧠 Contexto

Los procesos que ejecuta Camunda se definen mediante modelos BPMN.

Durante el desarrollo estos modelos se crean normalmente con **Camunda Modeler**, la herramienta oficial para diseñar procesos ejecutables.

En este ejercicio se creará un nuevo modelo BPMN que posteriormente será desplegado en el motor.

---

# Abrir Camunda Modeler

Iniciar la aplicación **Camunda Modeler** instalada anteriormente.

Al abrir la aplicación aparecerá la pantalla inicial.

Seleccionar:

```
New File → BPMN Diagram
```

Esto abrirá un nuevo diagrama vacío.

---

# Guardar el modelo en el proyecto

Antes de comenzar a modelar, guardar el archivo en el repositorio.

Seleccionar:

```
File → Save As
```

Guardar el archivo en el directorio:

```
model/
```

Nombre del archivo:

```
approval-process.bpmn
```

---

# Configurar el identificador del proceso

Seleccionar el **pool principal** del diagrama.

En el panel de propiedades configurar:

```
Process Id: approval-process
Name: Approval Process
Executable: true
```

Es importante que la opción **Executable** esté activada para que el motor pueda ejecutar el proceso.

---

# Verificar el archivo creado

Abrir una terminal en el directorio raíz del proyecto y ejecutar:

```bash
ls model
```

Debería aparecer el archivo:

```
approval-process.bpmn
```

---

# Abrir el modelo desde VS Code

Abrir el archivo:

```
model/approval-process.bpmn
```

Si la extensión BPMN está instalada, VS Code mostrará el diagrama visual.

Esto confirma que el modelo está correctamente guardado dentro del repositorio.

---

# Comprobación

El ejercicio se considera completado cuando:

* se crea un nuevo diagrama BPMN
* el proceso tiene el **Process Id `approval-process`**
* el archivo se guarda en el directorio `model`
* el archivo puede abrirse desde VS Code.
