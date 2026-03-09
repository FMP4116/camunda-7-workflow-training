# Usuarios y grupos

## 🎯 Objetivo

Crear **usuarios y grupos en Camunda** y comprender cómo se utilizan para gestionar tareas humanas dentro de un proceso.

---

## 🧠 Contexto

En un sistema de workflow real, las tareas humanas deben asignarse a **personas o roles organizativos**.

Camunda gestiona esto mediante dos conceptos:

```id="5b5e5o"
Users
Groups
```

Un **usuario** representa una persona concreta.

Un **grupo** representa un rol dentro de la organización.

Ejemplo:

```id="hld3m7"
usuarios: juan, maria, pedro
grupos: managers, reviewers
```

Las tareas BPMN pueden asignarse a **usuarios o grupos**.

---

# Abrir Camunda Admin

Arrancar la aplicación si no está en ejecución:

```bash id="taziv6"
cd workflow-app
mvn spring-boot:run
```

Abrir el navegador:

```id="t8k4v1"
http://localhost:8081/camunda/app/admin
```

Iniciar sesión con un usuario existente.

---

# Crear un nuevo usuario

Ir a la sección:

```id="y2er4m"
Users
```

Seleccionar:

```id="qahd8y"
Create New User
```

Introducir los siguientes datos:

```id="4tx7ba"
User ID: juan
First Name: Juan
Last Name: Pérez
Email: juan@empresa.com
Password: demo
```

Guardar el usuario.

---

# Crear un grupo

Ir a la sección:

```id="7ibunh"
Groups
```

Seleccionar:

```id="j0e08b"
Create New Group
```

Introducir:

```id="p0z5n3"
Group ID: reviewers
Name: Reviewers
Type: WORKFLOW
```

Guardar el grupo.

---

# Añadir un usuario al grupo

Abrir el grupo:

```id="e07ms8"
reviewers
```

Seleccionar:

```id="kg0a1r"
Add Member
```

Añadir el usuario:

```id="m10rcj"
juan
```

Ahora el usuario pertenece al grupo.

---

# Relación con BPMN

En los modelos BPMN se pueden asignar tareas a grupos.

Por ejemplo en una **User Task**:

```id="4n3j9p"
Candidate Groups = reviewers
```

Cuando el proceso llegue a esa tarea:

```id="y5a9o8"
la tarea aparecerá en Tasklist
para los usuarios del grupo
```

---

# Verificar en Tasklist

Abrir:

```id="02r4e7"
http://localhost:8081/camunda/app/tasklist
```

Iniciar sesión como:

```id="3l7ew0"
usuario: juan
password: demo
```

Las tareas asignadas al grupo deberían aparecer en la lista.

---

# Qué ocurre internamente

La asignación funciona de la siguiente forma:

```id="yo7tdu"
User Task
      │
      ▼
Candidate Group = reviewers
      │
      ▼
usuarios del grupo ven la tarea
```

Esto permite modelar **roles organizativos dentro del workflow**.

---

# Comprobación

El ejercicio se considera completado cuando:

* se crea un usuario
* se crea un grupo
* el usuario se añade al grupo
* el usuario puede ver tareas asignadas al grupo en Tasklist.
