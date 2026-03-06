# Acceso a Camunda Cockpit

## 🎯 Objetivo

Acceder a **Camunda Cockpit** para explorar el motor de procesos y verificar que la aplicación web de Camunda está disponible.

---

## 🧠 Contexto

Cuando se utiliza la dependencia:

```id="p6hmbq"
camunda-bpm-spring-boot-starter-webapp
```

Camunda instala automáticamente varias aplicaciones web de administración.

Una de ellas es **Cockpit**.

Cockpit permite:

* visualizar procesos desplegados
* inspeccionar instancias de proceso
* analizar el estado del motor
* investigar errores o incidentes

---

# Arrancar la aplicación

Ir al directorio del backend:

```bash id="owcc7s"
cd backend
```

Arrancar la aplicación:

```bash id="ju2z7b"
mvn spring-boot:run
```

Esperar hasta que aparezca en consola un mensaje similar a:

```
Tomcat started on port(s): 8081
```

(o el puerto configurado).

---

# Abrir Camunda Cockpit

Abrir el navegador y acceder a:

```
http://localhost:8081/camunda
```

Si la configuración es correcta se mostrará la pantalla de login de Camunda.

---

# Iniciar sesión

Si configuraste el usuario administrador en `application.properties`, usar las credenciales definidas.

Por ejemplo:

```
usuario: demo
password: demo
```

Si no se configuró usuario, puede aparecer acceso directo dependiendo de la configuración del proyecto.

---

# Explorar Cockpit

Una vez dentro de Cockpit observar las secciones disponibles.

Entre ellas:

* **Processes**
* **Decisions**
* **Deployments**
* **Jobs**

---

# Ver procesos desplegados

Ir a la sección:

```
Processes
```

Debería aparecer el proceso BPMN que se encuentra en:

```
src/main/resources/processes
```

Por ejemplo:

```
approval
```

Esto confirma que el motor ha desplegado correctamente el proceso.

---

# Explorar un proceso

Seleccionar uno de los procesos desplegados.

Cockpit mostrará:

* el diagrama BPMN
* estadísticas de ejecución
* instancias activas
* historial de procesos

---

# Qué hemos comprobado

Con este ejercicio se ha verificado que:

* el motor Camunda está activo
* los procesos BPMN se despliegan automáticamente
* Cockpit permite inspeccionar el estado del motor

---

# Comprobación

El ejercicio se considera completado cuando:

* la aplicación arranca correctamente
* se puede acceder a `/camunda`
* se visualizan procesos desplegados dentro de Cockpit.
