# Crear un JavaDelegate

## 🎯 Objetivo

Implementar la lógica de la **Service Task** creando una clase Java que será ejecutada por el motor Camunda.

---

## 🧠 Contexto

En el laboratorio anterior se creó una **Service Task** llamada:

```
Validar solicitud
```

Las Service Tasks representan actividades automáticas ejecutadas por el sistema.

En Camunda estas tareas suelen implementarse mediante una clase Java que implementa la interfaz:

```
JavaDelegate
```

Cuando el proceso alcance esta tarea, el motor ejecutará el código de esa clase.

---

# Crear el paquete de delegates

Ir al directorio del código Java:

```
backend/src/main/java
```

Crear el siguiente paquete:

```
com.example.workflow.delegate
```

---

# Crear la clase Java

Crear el archivo:

```
ValidarSolicitudDelegate.java
```

Ruta completa:

```
backend/src/main/java/com/example/workflow/delegate/ValidarSolicitudDelegate.java
```

---

# Implementar la interfaz JavaDelegate

Añadir el siguiente código:

```java
package com.example.workflow.delegate;

import org.camunda.bpm.engine.delegate.DelegateExecution;
import org.camunda.bpm.engine.delegate.JavaDelegate;
import org.springframework.stereotype.Component;

@Component
public class ValidarSolicitudDelegate implements JavaDelegate {

    @Override
    public void execute(DelegateExecution execution) {

        System.out.println("Ejecutando validación automática de la solicitud");

    }
}
```

---

# Qué hace esta clase

La clase implementa la interfaz:

```
JavaDelegate
```

Esto permite que el motor Camunda ejecute el método:

```
execute()
```

cuando el proceso llegue a la **Service Task**.

En este ejemplo la lógica es simple y solo imprime un mensaje en consola.

---

# Compilar el proyecto

Ir al directorio del backend:

```bash
cd backend
```

Compilar el proyecto:

```bash
mvn clean package
```

---

# Verificar que el proyecto compila

Si todo es correcto, Maven mostrará al final:

```
BUILD SUCCESS
```

---

# Comprobación

El ejercicio se considera completado cuando:

* se crea la clase `ValidarSolicitudDelegate`
* la clase implementa `JavaDelegate`
* el proyecto compila correctamente con Maven.
