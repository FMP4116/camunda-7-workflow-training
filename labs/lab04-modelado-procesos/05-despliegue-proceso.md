# Despliegue del proceso

## 🎯 Objetivo

Mover el modelo BPMN al directorio donde **Camunda lo desplegará automáticamente** y verificar que el proceso aparece en el motor.

---

## 🧠 Contexto

Durante los ejercicios anteriores los modelos BPMN se han guardado en:

```
model/
```

Este directorio sirve para **editar y versionar los modelos**, pero el motor Camunda no lo escanea automáticamente.

Camunda despliega automáticamente los procesos que se encuentran en:

```
src/main/resources/processes
```

Por lo tanto, para que el motor pueda ejecutar el proceso es necesario copiar el modelo a ese directorio.

---

# Copiar el modelo BPMN al backend

Desde la raíz del proyecto ejecutar:

```bash
cp model/approval-process.bpmn backend/src/main/resources/processes/
```

---

# Verificar que el archivo se ha copiado

Ejecutar:

```bash
ls backend/src/main/resources/processes
```

Debería aparecer el archivo:

```
approval-process.bpmn
```

---

# Arrancar la aplicación

Ir al directorio del backend:

```bash
cd backend
```

Arrancar la aplicación:

```bash
mvn spring-boot:run
```

Durante el arranque el motor Camunda escaneará el directorio `processes`.

Si encuentra modelos BPMN, los desplegará automáticamente.

---

# Verificar el despliegue en Cockpit

Abrir el navegador y acceder a:

```
http://localhost:8081/camunda
```

Entrar en **Cockpit**.

Ir a la sección:

```
Processes
```

Debería aparecer el proceso:

```
approval-process
```

---

# Explorar el proceso desplegado

Seleccionar el proceso en Cockpit.

Camunda mostrará:

* el diagrama BPMN
* las estadísticas del proceso
* instancias activas
* historial de ejecución

Esto confirma que el proceso ha sido desplegado correctamente.

---

# Qué ha ocurrido

Cuando la aplicación arranca:

```
Spring Boot inicia
        │
        ▼
Camunda escanea resources/processes
        │
        ▼
Se despliegan los modelos BPMN
        │
        ▼
Los procesos quedan disponibles en el motor
```

---

# Comprobación

El ejercicio se considera completado cuando:

* el archivo BPMN se copia a `resources/processes`
* la aplicación arranca correctamente
* el proceso aparece en **Camunda Cockpit**.
