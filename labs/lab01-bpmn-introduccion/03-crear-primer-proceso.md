# Crear primer proceso BPMN

## 🎯 Objetivo

Crear el **primer proceso BPMN** utilizando dos herramientas diferentes:

* **BPMN Editor de VS Code**
* **Camunda Modeler (aplicación oficial)**

Ambas herramientas permiten modelar procesos, pero **Camunda Modeler es la herramienta oficial recomendada para trabajar con Camunda**.

---

## 🧠 Contexto

En el laboratorio anterior instalamos una extensión BPMN en VS Code.
Esa extensión permite visualizar y editar diagramas BPMN directamente dentro del editor.

Sin embargo, en entornos profesionales es habitual utilizar **Camunda Modeler**, que es la herramienta oficial proporcionada por Camunda.

Ambas herramientas trabajan con el mismo formato:

```
.bpmn
```

Por lo tanto los modelos creados con una herramienta pueden abrirse con la otra.

---

## Herramientas disponibles

### BPMN Editor en VS Code

Ventajas:

* integrado en el editor
* cómodo para cambios rápidos
* no requiere salir de VS Code

Limitaciones:

* menos funcionalidades
* menor soporte para propiedades específicas de Camunda

---

### Camunda Modeler

Camunda Modeler es la **herramienta oficial para modelar procesos BPMN ejecutables en Camunda**.

Ventajas:

* editor BPMN completo
* soporte completo de Camunda
* panel avanzado de propiedades
* validación del modelo
* despliegue directo al motor

Por estas razones **será la herramienta recomendada durante el curso**.

---

## Instalar Camunda Modeler

Ir al sitio oficial:

```
https://camunda.com/download/modeler/
```

Descargar la versión correspondiente a tu sistema operativo.

Una vez descargado:

1. instalar la aplicación
2. abrir Camunda Modeler

La interfaz mostrará un editor de procesos BPMN.

---

# Crear proceso con Camunda Modeler

## Crear un nuevo modelo

Abrir Camunda Modeler.

Seleccionar:

```
New File → BPMN Diagram
```

Se abrirá un nuevo diagrama vacío.

---

## Crear el proceso

Construir el siguiente flujo:

```
Inicio → Revisar solicitud → Fin
```

Pasos:

1. arrastrar un **Start Event**
2. arrastrar una **Task**
3. arrastrar un **End Event**
4. conectar los elementos con **Sequence Flow**

---

## Nombrar los elementos

Asignar los siguientes nombres:

Start Event

```
Inicio
```

Task

```
Revisar solicitud
```

End Event

```
Fin
```

---

## Guardar el modelo

Guardar el archivo en el directorio:

```
model/
```

Nombre del archivo:

```
primer-proceso.bpmn
```

---

# Crear proceso usando VS Code

También es posible editar el proceso directamente desde VS Code.

Abrir el archivo:

```
model/primer-proceso.bpmn
```

Si la extensión BPMN está instalada se mostrará el diagrama.

Desde aquí se pueden:

* mover elementos
* renombrar tareas
* modificar el flujo

Esto permite trabajar sin salir del entorno de desarrollo.

---

## Comparación de herramientas

| Herramienta         | Uso recomendado             |
| ------------------- | --------------------------- |
| VS Code BPMN Editor | cambios rápidos             |
| Camunda Modeler     | diseño completo de procesos |

Durante el curso utilizaremos principalmente **Camunda Modeler** para modelar los procesos.

---

## Resultado esperado

El modelo creado debería representar el siguiente flujo:

```
Inicio
   │
   ▼
Revisar solicitud
   │
   ▼
Fin
```

El archivo generado:

```
model/primer-proceso.bpmn
```

se utilizará en los siguientes laboratorios.
