# Explorar Camunda Tasklist

## 🎯 Objetivo

Aprender a utilizar **Camunda Tasklist** para gestionar **tareas humanas** dentro de un proceso.

---

## 🧠 Contexto

Cuando un proceso BPMN alcanza una **User Task**, el motor Camunda:

```id="1f2qpg"
crea una tarea
la asigna a un usuario o grupo
espera a que alguien la complete
```

Estas tareas se gestionan desde la aplicación web:

```id="t6t9n3"
Tasklist
```

Tasklist es la interfaz utilizada por los **usuarios del negocio** para interactuar con el proceso.

---

# Abrir Tasklist

Arrancar la aplicación si no está en ejecución:

```bash id="q5b9ok"
cd workflow-app
mvn spring-boot:run
```

Abrir el navegador:

```id="n1t7kp"
http://localhost:8081/camunda/app/tasklist
```

---

# Iniciar sesión

Introducir las credenciales del usuario configurado.

Por ejemplo:

```id="3b7j02"
usuario: demo
password: demo
```

---

# Ver las tareas disponibles

La pantalla principal mostrará una lista de tareas.

Estas tareas corresponden a **User Tasks activas dentro de los procesos**.

Ejemplo:

```id="5qhb6p"
Aprobar solicitud de juan
```

Cada tarea representa trabajo pendiente dentro del proceso.

---

# Explorar una tarea

Seleccionar una tarea.

Tasklist mostrará información como:

```id="axp9m3"
nombre de la tarea
proceso al que pertenece
variables del proceso
formulario asociado
```

---

# Completar una tarea

Si la tarea tiene un formulario aparecerán campos que el usuario debe completar.

Ejemplo:

```id="74p1sr"
Solicitud aprobada = true / false
```

Seleccionar un valor.

Presionar:

```id="nb6qj2"
Complete
```

---

# Qué ocurre cuando se completa una tarea

Cuando el usuario completa la tarea:

```id="e2hypt"
Tasklist envía datos al motor
        │
        ▼
Camunda guarda variables del formulario
        │
        ▼
el proceso continúa su ejecución
```

El flujo del proceso seguirá hacia la siguiente actividad.

---

# Ver el resultado en Cockpit

Abrir:

```id="a9lpt4"
http://localhost:8081/camunda
```

Ir a **Cockpit**.

Abrir el proceso:

```id="6kkrqn"
approval-process
```

Se podrá observar cómo la instancia ha avanzado después de completar la tarea.

---

# Qué se ha aprendido

Tasklist permite:

```id="9yut2v"
gestionar tareas humanas
completar formularios
actualizar variables del proceso
avanzar el flujo BPMN
```

Es la herramienta que utilizan normalmente los **usuarios finales del workflow**.

---

# Comprobación

El ejercicio se considera completado cuando:

* se accede a **Tasklist**
* se localiza una tarea del proceso
* se completa la tarea
* el proceso continúa su ejecución.
