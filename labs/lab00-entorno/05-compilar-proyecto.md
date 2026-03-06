# Compilar el proyecto

## 🎯 Objetivo

Compilar la aplicación backend utilizando **Maven** para verificar que el proyecto puede construirse correctamente.

---

## 🧠 Contexto

El proyecto backend está basado en **Spring Boot** y utiliza **Maven** como herramienta de construcción.

Maven se encarga de:

* descargar dependencias
* compilar el código Java
* ejecutar tests
* generar el artefacto de la aplicación

El archivo que define el proyecto Maven es:

```
pom.xml
```

---

## 📍 Ir al directorio del backend

Abrir una terminal en VS Code y cambiar al directorio del backend:

```bash
cd backend
```

---

## 🔧 Compilar el proyecto

Ejecutar el siguiente comando:

```bash
mvn clean install
```

---

## 📦 Qué hace este comando

El comando ejecuta varias fases del ciclo de vida de Maven:

| Fase    | Descripción                                  |
| ------- | -------------------------------------------- |
| clean   | elimina compilaciones anteriores             |
| compile | compila el código Java                       |
| test    | ejecuta los tests                            |
| package | crea el artefacto de la aplicación           |
| install | instala el artefacto en el repositorio local |

Durante este proceso Maven descargará las dependencias necesarias desde los repositorios remotos.

La primera compilación puede tardar unos minutos.

---

## 📌 Resultado esperado

Si la compilación es correcta, al final de la ejecución aparecerá un mensaje similar a:

```
BUILD SUCCESS
```

---

## 📁 Directorio generado

Después de compilar, Maven creará el directorio:

```
target/
```

Este directorio contiene los artefactos generados durante la compilación.

---

## 🔎 Verificar el resultado

Puedes comprobar el contenido generado ejecutando:

```bash
ls target
```

Debería aparecer un archivo `.jar` correspondiente a la aplicación.

---

## ⚠️ Posibles problemas

Si aparece algún error:

* verificar que **Java 17** está instalado
* verificar que **Maven** funciona correctamente
* comprobar que el comando se ejecuta dentro del directorio `backend`

---

## ✅ Comprobación

El paso se considera completado cuando:

* el comando `mvn clean install` finaliza correctamente
* aparece el mensaje **BUILD SUCCESS**
* existe el directorio `target` en el proyecto backend.
