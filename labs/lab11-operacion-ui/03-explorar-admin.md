# Explorar Camunda Admin

## 🎯 Objetivo

Utilizar **Camunda Admin** para gestionar **usuarios, grupos y autorizaciones** del motor de procesos.

---

## 🧠 Contexto

Camunda incluye una aplicación web llamada:

```id="on38h8"
Admin
```

Esta herramienta permite gestionar la **seguridad del motor**.

Con Admin se pueden crear:

```id="zmpys3"
usuarios
grupos
miembros de grupo
autorizaciones
```

Esto permite controlar **quién puede acceder a Tasklist, Cockpit o a determinadas tareas**.

---

# Abrir Camunda Admin

Arrancar la aplicación si no está en ejecución:

```bash id="2d7kz3"
cd workflow-app
mvn spring-boot:run
```

Abrir el navegador:

```id="72rz5m"
http://localhost:8081/camunda/app/admin
```

---

# Iniciar sesión

Introducir las credenciales del usuario administrador.

Ejemplo:

```id="v4j9r1"
usuario: demo
password: demo
```

---

# Explorar la interfaz

La interfaz de **Admin** contiene varias secciones.

Entre ellas:

```id="0z8z1c"
Users
Groups
Authorizations
System
```

---

# Ver usuarios del sistema

Ir a la sección:

```id="r92b6q"
Users
```

Aquí se pueden ver los usuarios registrados en el motor.

Seleccionar un usuario para ver sus detalles.

---

# Ver grupos

Ir a:

```id="j9bqos"
Groups
```

Los grupos se utilizan para organizar usuarios.

Ejemplo:

```id="7vhz4n"
managers
reviewers
administrators
```

Las tareas BPMN pueden asignarse a grupos mediante:

```id="nyz5z4"
Candidate Groups
```

---

# Crear un nuevo grupo

Seleccionar:

```id="l5s9n0"
Create New Group
```

Introducir:

```id="v3y0rf"
Group ID: reviewers
Name: Reviewers
```

Guardar el grupo.

---

# Añadir un usuario al grupo

Abrir el grupo creado.

Seleccionar:

```id="d4k9xn"
Add Member
```

Elegir el usuario:

```id="69kk0t"
demo
```

Ahora ese usuario pertenece al grupo.

---

# Relación con el proceso BPMN

En el modelo BPMN se pueden asignar tareas a grupos.

Ejemplo:

```id="t2hlkr"
Candidate Groups = reviewers
```

Cuando el proceso llegue a la **User Task**, cualquier usuario del grupo podrá realizarla.

---

# Verificar en Tasklist

Abrir:

```id="n0k5a3"
http://localhost:8081/camunda/app/tasklist
```

El usuario del grupo podrá ver las tareas asignadas al grupo.

---

# Qué se ha aprendido

La aplicación **Admin** permite gestionar la seguridad del motor.

Con ella se puede:

```id="yt99se"
crear usuarios
crear grupos
asignar usuarios a grupos
controlar accesos
```

Esto permite integrar el workflow con **roles organizativos reales**.

---

# Comprobación

El ejercicio se considera completado cuando:

* se accede a **Camunda Admin**
* se exploran usuarios y grupos
* se crea un nuevo grupo
* se añade un usuario al grupo.
