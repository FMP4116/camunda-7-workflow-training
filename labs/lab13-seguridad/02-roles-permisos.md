# Roles y permisos

## 🎯 Objetivo

Comprender cómo Camunda controla el acceso a recursos mediante **roles y permisos**.

---

## 🧠 Contexto

Camunda utiliza un sistema de **autorizaciones** para controlar qué usuarios pueden realizar determinadas acciones.

Los permisos pueden aplicarse a diferentes tipos de recursos.

Ejemplos:

```id="ub8n9l"
procesos
tareas
instancias de proceso
usuarios
grupos
```

Los permisos se asignan normalmente a **usuarios o grupos**.

---

# Acceder a la sección de autorizaciones

Arrancar la aplicación si no está en ejecución:

```bash id="7g6a3f"
cd workflow-app
mvn spring-boot:run
```

Abrir la interfaz de administración:

```id="d0q1mp"
http://localhost:8081/camunda/app/admin
```

Ir a la sección:

```id="g4xhs7"
Authorizations
```

---

# Crear una autorización

Seleccionar:

```id="qpxa1y"
Create New Authorization
```

Configurar los siguientes valores.

---

# Tipo de autorización

Seleccionar:

```id="m3oyp4"
Grant
```

Esto indica que se está **concediendo un permiso**.

---

# Seleccionar el grupo

Elegir el grupo creado anteriormente.

```id="5h75w9"
reviewers
```

---

# Seleccionar el recurso

Seleccionar el tipo de recurso:

```id="9r3rsl"
Process Definition
```

Esto permitirá controlar el acceso a procesos.

---

# Seleccionar el proceso

Introducir el identificador del proceso:

```id="6d5l1g"
approval-process
```

---

# Seleccionar permisos

Activar los siguientes permisos:

```id="j1xq06"
READ
READ_INSTANCE
```

Esto permitirá a los miembros del grupo:

```id="6aybnd"
ver el proceso
ver instancias del proceso
```

Guardar la autorización.

---

# Verificar el comportamiento

Abrir **Tasklist** o **Cockpit**.

Iniciar sesión con el usuario:

```id="o8p2fw"
juan
```

El usuario podrá visualizar el proceso y sus instancias.

---

# Ejemplo de control de acceso

Con autorizaciones se pueden definir reglas como:

```id="11ndrf"
solo managers pueden iniciar procesos
solo reviewers pueden completar tareas
solo administradores pueden modificar procesos
```

Esto permite implementar políticas de seguridad dentro del sistema.

---

# Cómo funciona el modelo de permisos

El sistema de autorización funciona así:

```id="m6i1o4"
usuario pertenece a grupo
        │
        ▼
grupo tiene permisos
        │
        ▼
Camunda permite o bloquea la acción
```

---

# Comprobación

El ejercicio se considera completado cuando:

* se crea una autorización
* se asigna a un grupo
* el grupo obtiene permisos sobre el proceso
* el usuario del grupo puede acceder al proceso.
