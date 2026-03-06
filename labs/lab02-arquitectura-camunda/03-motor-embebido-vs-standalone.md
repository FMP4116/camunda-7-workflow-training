# Motor embebido vs motor standalone

## 🎯 Objetivo

Comprender las dos formas principales de ejecutar Camunda comparando:

* motor **embebido**
* motor **standalone**

y verificar cuál de ellas se está utilizando en el proyecto del curso.

---

## 🧠 Contexto

Camunda puede ejecutarse de distintas maneras dependiendo de la arquitectura del sistema.

Las dos configuraciones más habituales son:

```id="xaqb9n"
Motor embebido
Motor standalone
```

Cada enfoque tiene características diferentes.

---

# Motor embebido

En este modelo el **motor de procesos se ejecuta dentro de la propia aplicación**.

Arquitectura:

```id="zk0fkh"
Spring Boot Application
        │
        ▼
Camunda Process Engine
        │
        ▼
Database
```

El motor se inicializa cuando arranca la aplicación.

Ventajas:

* integración directa con el código
* despliegue sencillo
* arquitectura simple

Este es el enfoque utilizado en este curso.

---

# Motor standalone

En este modelo el motor se ejecuta **como un sistema independiente**.

Arquitectura:

```id="6x78ia"
Application A
Application B
Application C
      │
      ▼
Camunda Process Engine (standalone)
      │
      ▼
Database
```

Las aplicaciones interactúan con el motor mediante:

* REST API
* mensajería
* external tasks

Ventajas:

* motor centralizado
* múltiples aplicaciones pueden usar el mismo motor
* escalado independiente

---

# Identificar el tipo de motor del proyecto

Abrir el archivo:

```id="0r9y1x"
pom.xml
```

Buscar la dependencia:

```id="60m4v3"
camunda-bpm-spring-boot-starter-webapp
```

Esta dependencia indica que el proyecto utiliza:

```id="i9he9m"
motor embebido
```

El starter de Spring Boot se encarga de:

* crear el ProcessEngine
* inicializar la base de datos
* desplegar los procesos BPMN
* arrancar las aplicaciones web de Camunda

---

# Verificar el arranque del motor

Arrancar la aplicación:

```bash id="7ns9ff"
mvn spring-boot:run
```

Durante el arranque aparecerá un mensaje similar a:

```
ENGINE-00001 Process Engine default created
```

Esto indica que el motor embebido se ha inicializado dentro de la aplicación.

---

# Comparación de arquitecturas

| Característica         | Motor embebido          | Motor standalone          |
| ---------------------- | ----------------------- | ------------------------- |
| Ubicación del motor    | dentro de la aplicación | sistema independiente     |
| Integración con código | directa                 | mediante API              |
| Complejidad            | baja                    | mayor                     |
| Uso típico             | microservicios          | plataformas centralizadas |

---

# Comprobación

El ejercicio se considera completado cuando:

* se identifica la dependencia Camunda en el `pom.xml`
* se comprende que el proyecto utiliza **motor embebido**
* se entiende la diferencia entre motor embebido y standalone.
