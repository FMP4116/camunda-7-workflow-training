# Crear una User Task

## 🎯 Objetivo

Configurar la **User Task** del proceso para que pueda ser gestionada desde **Camunda Tasklist**.

---

## 🧠 Contexto

En el modelo BPMN se añadió previamente una tarea humana llamada:

```id="5f3q4s"
Aprobar solicitud
```

Cuando el proceso alcanza una **User Task**, el motor Camunda:

1. crea una tarea
2. la asigna a un usuario o grupo
3. espera a que alguien complete la tarea

Estas tareas se gestionan desde la aplicación web:

```id="c6h34p"
/camunda/app/tasklist
```

Para que la tarea pueda aparecer correctamente en Tasklist es necesario configurar **quién puede realizarla**.

---

# Abrir el modelo BPMN

Abrir el archivo:

```id="8s0c4q"
model/approval-process.bpmn
```

Editar el modelo con **Camunda Modeler**.

---

# Seleccionar la User Task

Seleccionar la tarea:

```id="n1x0lq"
Aprobar solicitud
```

---

# Configurar el asignatario

En el panel de propiedades buscar la sección:

```id="0a3x4e"
Assignment
```

Configurar el campo:

```id="4o3m1q"
Assignee
```

Introducir el valor:

```id="r5a9h2"
demo
```

Esto indica que la tarea será asignada al usuario **demo**.

---

# Guardar el modelo

Guardar los cambios:

```id="y7e2jq"
model/approval-process.bpmn
```

---

# Copiar el modelo al backend

Actualizar el modelo desplegado en el backend:

```bash id="j6g1oz"
cp model/approval-process.bpmn backend/src/main/resources/processes/
```

---

# Reiniciar la aplicación

Ir al directorio del backend:

```bash id="a6c9pn"
cd backend
```

Arrancar la aplicación:

```bash id="w4n5lp"
mvn spring-boot:run
```

---

# Iniciar un proceso

Cuando el proceso se ejecute:

1. se ejecutará la **Service Task**
2. el proceso llegará a la **User Task**

En ese momento el motor creará una tarea para el usuario configurado.

---

# Verificar en Tasklist

Abrir en el navegador:

```id="u3y8gx"
http://localhost:8081/camunda/app/tasklist
```

Iniciar sesión con el usuario:

```id="x5r2bc"
demo
```

Debería aparecer la tarea:

```id="t4p8zn"
Aprobar solicitud
```

---

# Completar la tarea

Seleccionar la tarea y presionar:

```id="q9d6tm"
Complete
```

Esto permitirá que el proceso continúe hasta el evento de fin.

---

# Flujo del proceso

El proceso ahora se ejecuta de la siguiente forma:

```id="f8s7b2"
Inicio
   │
   ▼
Validar solicitud (Service Task)
   │
   ▼
Aprobar solicitud (User Task)
   │
   ▼
Fin
```

---

# Comprobación

El ejercicio se considera completado cuando:

* la User Task tiene configurado el **assignee**
* la tarea aparece en **Tasklist**
* el usuario puede completar la tarea y finalizar el proceso.
