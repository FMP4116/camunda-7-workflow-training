# Testing de procesos

## 🎯 Objetivo

Crear un **test automatizado** que verifique la ejecución de un proceso BPMN utilizando **JUnit y el motor Camunda**.

---

## 🧠 Contexto

Los procesos BPMN pueden probarse igual que cualquier otro componente de software.

Un test puede verificar:

```id="7a6n8p"
que un proceso se inicia correctamente
qué tareas se ejecutan
qué variables se generan
si el proceso termina correctamente
```

Camunda permite ejecutar estos tests utilizando el motor embebido dentro del test.

---

# Crear el archivo de test

Crear el archivo:

```id="g9k2o1"
workflow-app/src/test/java/com/example/workflow/ProcesoApprovalTest.java
```

---

# Añadir el test básico

Añadir el siguiente código:

```java id="f1q2z9"
package com.example.workflow;

import org.camunda.bpm.engine.RuntimeService;
import org.camunda.bpm.engine.runtime.ProcessInstance;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;

import static org.assertj.core.api.Assertions.assertThat;

@SpringBootTest
public class ProcesoApprovalTest {

    @Autowired
    private RuntimeService runtimeService;

    @Test
    void iniciarProceso() {

        ProcessInstance instance = runtimeService.startProcessInstanceByKey("approval-process");

        assertThat(instance).isNotNull();
        assertThat(instance.isEnded()).isFalse();

    }
}
```

Este test verifica que el proceso puede iniciarse correctamente.

---

# Ejecutar los tests

En la **terminal**, desde la **raíz del repositorio** ejecuta `cd workflow-app`. Luego:

Ejecutar los tests:

```bash id="f0h6c8"
mvn test
```

El test debería ejecutarse correctamente.

---

# Añadir variables al test

Modificar el test para iniciar el proceso con variables.

```java id="t3v5j7"
@Test
void iniciarProcesoConVariables() {

    ProcessInstance instance = runtimeService.startProcessInstanceByKey(
            "approval-process",
            java.util.Map.of(
                    "solicitante", "juan",
                    "importe", 1000,
                    "tipoSolicitud", "COMPRA"
            )
    );

    assertThat(instance).isNotNull();
}
```

Esto permite probar distintos escenarios del proceso.

---

# Qué ocurre durante el test

Durante la ejecución del test:

```id="b9e0k1"
Spring Boot inicia el contexto
        │
        ▼
Camunda arranca el motor
        │
        ▼
se despliega el proceso BPMN
        │
        ▼
el test ejecuta el proceso
```

Esto permite validar el comportamiento del workflow automáticamente.

---

# Ventajas del testing de procesos

El testing permite:

```id="y2v4d6"
detectar errores en modelos BPMN
validar reglas de negocio
probar diferentes escenarios
evitar regresiones
```

---

# Comprobación

El ejercicio se considera completado cuando:

* se crea un test para el proceso
* el test inicia el proceso BPMN
* el test se ejecuta correctamente con `mvn test`.
