# Autorizaciones en procesos y tareas

## 🎯 Objetivo

Configurar **autorizaciones específicas sobre tareas y procesos** para controlar quién puede interactuar con el workflow.

---

## 🧠 Contexto

Camunda permite definir autorizaciones muy específicas sobre distintos recursos del motor.

Entre ellos:

```id="0v6gqp"
Process Definition
Process Instance
Task
Deployment
User
Group
```

Esto permite controlar quién puede:

```id="kwhu7o"
ver procesos
iniciar procesos
completar tareas
modificar instancias
```

En este ejercicio se configurarán permisos sobre **tareas humanas del proceso**.

---

# Acceder a Camunda Admin

Arrancar la aplicación si no está en ejecución:

```bash id="bnt2t4"
cd workflow-app
mvn spring-boot:run
```

Abrir el navegador:

```id="0hjh7m"
http://localhost:8081/camunda/app/admin
```

Ir a la sección:

```id="od3ub3"
Authorizations
```

---

# Crear una nueva autorización

Seleccionar:

```id="2qhlz5"
Create New Authorization
```

---

# Configurar el tipo

Seleccionar:

```id="nd5n1b"
Grant
```

Esto significa que se están **concediendo permisos**.

---

# Seleccionar el grupo

Seleccionar el grupo creado anteriormente:

```id="9j8x0d"
reviewers
```

---

# Seleccionar el recurso

Elegir el recurso:

```id="qz1j8o"
Task
```

Esto permite controlar el acceso a tareas humanas.

---

# Seleccionar permisos

Activar los permisos:

```id="6c1mdu"
READ
UPDATE
```

Esto permitirá a los usuarios del grupo:

```id="y5e4ox"
ver tareas
completar tareas
```

Guardar la autorización.

---

# Probar la autorización

Abrir **Tasklist**:

```id="0zqj5x"
http://localhost:8081/camunda/app/tasklist
```

Iniciar sesión como:

```id="o4y5zh"
usuario: juan
password: demo
```

Localizar una tarea del proceso.

El usuario debería poder:

```id="v1k3x3"
ver la tarea
completar la tarea
```

---

# Probar restricciones

Si un usuario no pertenece al grupo autorizado:

```id="t52f0y"
no podrá ver
ni completar tareas
```

Esto demuestra que el sistema de autorizaciones controla el acceso al workflow.

---

# Cómo funciona internamente

Cuando un usuario intenta interactuar con una tarea:

```id="y0pnid"
usuario solicita acción
        │
        ▼
Camunda verifica permisos
        │
        ▼
si tiene permiso → acción permitida
si no → acción bloqueada
```

---

# Comprobación

El ejercicio se considera completado cuando:

* se crea una autorización sobre **Task**
* se asigna al grupo `reviewers`
* el usuario del grupo puede completar tareas
* otros usuarios no autorizados no pueden hacerlo.
