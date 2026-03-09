# Crear primer proceso BPMN

## 🎯 Objetivo

Crear el **primer proceso BPMN** utilizando dos herramientas diferentes:

* **BPMN Editor de VS Code**
* **Camunda Modeler (aplicación oficial)**

Ambas permiten modelar procesos; **Camunda Modeler es la herramienta oficial recomendada** para trabajar con Camunda. Si no sabes cuál usar, empieza por Camunda Modeler.

---

## 🧠 Contexto

En el laboratorio anterior vimos la extensión BPMN en VS Code: sirve para ver y editar diagramas BPMN sin salir del editor.

En entornos profesionales se suele usar **Camunda Modeler**, la herramienta oficial de Camunda. Los dos trabajan con archivos `.bpmn`, así que lo que crees en uno puedes abrirlo en el otro. **Este lab es 100 % modelado**: no se requiere que el backend tenga Camunda instalado; eso se hace en el lab03.

---

## Herramientas disponibles

### BPMN Editor en VS Code

Está dentro del propio editor: cómodo para retoques rápidos, pero con menos opciones y menos soporte para cosas específicas de Camunda.

### Camunda Modeler

Es la **herramienta oficial** para diseñar procesos que luego se ejecutan en Camunda. Tiene editor completo, panel de propiedades, validación y despliegue directo al motor. **En el curso la usaremos como referencia** para modelar.

---

## Instalar Camunda Modeler

Entra en:

```
https://camunda.com/download/modeler/
```

Descarga la versión de tu sistema (Windows, Mac o Linux). Cuando termine:

1. Instala la aplicación como cualquier programa.
2. Ábrela. Verás una ventana de bienvenida o un editor vacío; esa es la interfaz donde se crean los diagramas.

---

# Crear proceso con Camunda Modeler

## Crear un nuevo modelo

Con **Camunda Modeler** abierto:

1. En la **parte superior** de la ventana está el menú **File**. Haz clic en **File**.
2. En el desplegable verás **New File**. Haz clic ahí.
3. Te mostrará opciones de tipo de archivo. Elige **BPMN Diagram** (es el que usamos para procesos).
4. Se abrirá un **diagrama vacío**: un canvas blanco en el centro y, normalmente, una **barra o paleta a la izquierda** con los elementos que puedes arrastrar (eventos, tareas, gateways, etc.). Si no ves la paleta, busca un panel lateral izquierdo o un botón que muestre “palette” o “elementos”.

A partir de aquí trabajamos en ese canvas.

---

## Crear el flujo del proceso

Vamos a montar este flujo:

```
Inicio → Revisar solicitud → Fin
```

**Dónde están las cosas:** En la **paleta de la izquierda** (o en el panel de elementos) verás iconos para:

* **Start Event** (círculo simple) — es el inicio del proceso.
* **Task** (rectángulo con bordes redondeados) — una actividad.
* **End Event** (círculo con borde grueso o con una raya) — el fin del proceso.
* **Sequence Flow** (flecha o conector) — une elementos en orden.

**Pasos:**

1. **Arrastra** un **Start Event** desde la paleta al canvas y suéltalo.
2. **Arrastra** una **Task** y colócala a la derecha del inicio.
3. **Arrastra** un **End Event** y colócalo a la derecha de la tarea.
4. Para **unir** los elementos: selecciona el **Sequence Flow** en la paleta (la flecha), haz clic en el **Start Event** y arrastra hasta la **Task**; luego haz clic en la **Task** y arrastra hasta el **End Event**. Deberías ver las flechas conectando Inicio → Revisar solicitud → Fin.

Si en tu versión el conector se elige de otra forma (por ejemplo, haciendo hover sobre un elemento y saliendo una flecha), usa ese método: el objetivo es que los tres elementos queden enlazados en ese orden.

---

## Nombrar los elementos

En BPMN cada elemento puede tener un nombre (etiqueta) que se muestra en el diagrama. Así sabes qué es cada cosa.

1. **Haz doble clic** en el **Start Event** (o selecciónalo y busca el panel de **Properties** / Propiedades, que suele estar **a la derecha** o abajo). Donde diga “Name” o “Nombre”, escribe: **Inicio**.
2. Haz lo mismo con la **Task**: nómbrala **Revisar solicitud**.
3. Y con el **End Event**: **Fin**.

El panel de propiedades sirve para cambiar nombre, id y otras opciones del elemento seleccionado. Si no ves el panel, suele abrirse al seleccionar un elemento o desde un menú tipo **Window** → **Show Properties**.

---

## Guardar el modelo

1. Arriba, menú **File** → **Save** (o **Save As** si es la primera vez).
2. Navega hasta la carpeta **model/** del repositorio del curso (en la misma raíz donde están la carpeta **labs** y el **README** del proyecto).
3. Como nombre de archivo pon: **primer-proceso.bpmn**.
4. Guarda. Comprueba que en `model/` aparece el archivo `primer-proceso.bpmn`.

---

# Crear proceso usando VS Code

Si prefieres trabajar todo desde el editor:

1. Abre el archivo **model/primer-proceso.bpmn** en VS Code (si ya lo creaste en Camunda Modeler, ábrelo desde aquí).
2. Si tienes instalada la **extensión BPMN**, deberías ver el diagrama (vista gráfica). Desde ahí puedes mover elementos, cambiar nombres y ajustar el flujo sin abrir Camunda Modeler.

Así puedes hacer cambios rápidos sin cambiar de herramienta.

---

## Comparación de herramientas

| Herramienta         | Uso recomendado             |
| ------------------- | --------------------------- |
| VS Code BPMN Editor | cambios rápidos en el repo   |
| Camunda Modeler     | diseñar el proceso completo |

En el curso usaremos sobre todo **Camunda Modeler** para modelar; VS Code queda como opción para retoques.

---

## Resultado esperado

El modelo debe representar este flujo:

```
Inicio
   │
   ▼
Revisar solicitud
   │
   ▼
Fin
```

El archivo **model/primer-proceso.bpmn** es el que usaremos en los siguientes laboratorios.
