# Estructura del proyecto Spring Boot

## 🎯 Objetivo

Explorar la estructura de una aplicación **Spring Boot** identificando dónde se encuentran:

* el código Java
* los recursos del proyecto
* los procesos BPMN
* la configuración de la aplicación

Además se verificará que **Spring Boot carga automáticamente los recursos del directorio `resources`**.

---

## 🧠 Contexto

Las aplicaciones Spring Boot siguen una estructura estándar de directorios.

Esta estructura permite que el framework encuentre automáticamente:

* clases Java
* archivos de configuración
* recursos del proyecto
* modelos BPMN

Camunda aprovecha esta estructura para **localizar automáticamente los procesos BPMN**.

---

# Explorar el proyecto backend

Ir al directorio del backend:

```bash
cd backend
```

Mostrar la estructura del proyecto:

```bash
tree src
```

La estructura debería ser similar a:

```
src
├── main
│   ├── java
│   └── resources
└── test
```

---

# Identificar el código de la aplicación

Ir al directorio:

```
src/main/java
```

Localizar la clase principal de la aplicación.

Abrir el archivo:

```
WorkflowAppApplication.java
```

Buscar la anotación:

```java
@SpringBootApplication
```

Esta anotación indica que esta clase es **el punto de arranque de Spring Boot**.

---

# Identificar los recursos del proyecto

Ir al directorio:

```
src/main/resources
```

Aquí se encuentran los recursos cargados por la aplicación.

Por ejemplo:

* configuración
* archivos estáticos
* modelos BPMN

---

# Ver dónde se almacenan los procesos BPMN

Ir al directorio:

```
src/main/resources/processes
```

Aquí se almacenan los modelos BPMN utilizados por Camunda.

Por ejemplo:

```
approval.bpmn
```

---

# Verificar que Spring Boot carga los recursos

Crear un archivo de prueba dentro del directorio `resources`.

Crear el archivo:

```
src/main/resources/test-resource.txt
```

Contenido del archivo:

```
Spring Boot resources test
```

Guardar el archivo.

---

# Verificar que el archivo está en el classpath

Compilar el proyecto:

```bash
mvn clean package
```

Después de compilar, abrir el directorio generado:

```
target/classes
```

Ejecutar:

```bash
ls target/classes
```

Debería aparecer el archivo:

```
test-resource.txt
```

Esto demuestra que **Spring Boot copia automáticamente los recursos al classpath durante la compilación**.

---

# Qué significa esto para Camunda

El motor Camunda utiliza este mismo mecanismo para localizar los procesos BPMN.

Cuando la aplicación arranca:

1. Spring Boot carga los recursos del classpath
2. Camunda escanea el directorio `processes`
3. los archivos BPMN encontrados se despliegan automáticamente

---

# Comprobación

El ejercicio se considera completado cuando:

* se ha identificado la estructura del proyecto
* se ha localizado el directorio `resources`
* se ha creado un recurso de prueba
* se ha comprobado que el archivo aparece en `target/classes`.
