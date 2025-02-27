# Implementación del Patrón de Diseño Builder

## Información del Proyecto
- **Universidad:** Universidad de La Sabana  
- **Facultad:** Facultad de Ingeniería  
- **Materia:** Diseño y Arquitectura de Software  
- **Profesor:** Cesar Augusto Vega Fernandez  

## Integrantes del Proyecto
| Nombre | Correo Electrónico |
|--------|-------------------|
| Juan Pablo Benitez Bernal | juanbenbe@unisabana.edu.co |
| Mariana Valle Moreno | marianavamo@unisabana.edu.co |

## Estructura de la Documentación
- [1. Descripción del Patrón](#1-descripción-del-patrón)
- [2. Estructura del Proyecto](#2-estructura-del-proyecto)
- [3. Instrucciones de Instalación](#3-instrucciones-de-instalación)
- [4. Ejemplo de Ejecución](#4-ejemplo-de-ejecución)
- [5. Diagrama UML](#5-diagrama-uml)
- [6. Explicación de la Implementación](#6-explicación-de-la-implementación)

---

## 1. Descripción del Patrón
El Patrón Builder es un patrón de diseño creacional que permite construir objetos complejos paso a paso, separando su construcción de su representación final.

### Características principales:
- Facilita la creación de objetos con múltiples configuraciones.
- Evita constructores con demasiados parámetros.
- Permite construir diferentes representaciones del mismo objeto sin duplicar código.

---

## 2. Estructura del Proyecto
La estructura del proyecto sigue el estándar de Maven:

```
proyecto-builder
│
├── pom.xml                # Archivo de configuración de Maven
├── README.md              # Documentación del proyecto
└── src
    ├── main
    │   ├── java
    │   │   └── com/proyecto/builder
    │   │       ├── builders
    │   │       │   ├── Builder.java
    │   │       │   ├── CarBuilder.java
    │   │       │   └── CarManualBuilder.java
    │   │       ├── cars
    │   │       │   ├── Car.java
    │   │       │   ├── CarType.java
    │   │       │   ├── Manual.java
    │   │       ├── components
    │   │       │   ├── Engine.java
    │   │       │   ├── GPSNavigator.java
    │   │       │   ├── Transmission.java
    │   │       │   ├── TripComputer.java
    │   │       ├── director
    │   │       │   ├── Director.java
    │   │       │   ├── Demo.java
    │   └── resources      
    └── test
```

---

## 3. Instrucciones de Instalación

1. **Clonar el repositorio:**
```bash
git clone https://github.com/JuanBenitez21/Patron_Builder.git
cd Patron_Builder
```

2. **Compilar el proyecto:**
```bash
mvn clean compile
```

3. **Ejecutar el proyecto:**
```bash
mvn exec:java -Dexec.mainClass="director.Demo"
```

---

## 4. Ejemplo de Ejecución
Al ejecutar el programa, deberías ver la siguiente salida:

```
Car built:
SPORTS_CAR
Car manual built:
Type of car: SPORTS_CAR
Count of seats: 2
Engine: volume - 3.0; mileage - 0.0
Transmission: SEMI_AUTOMATIC
Trip Computer: Functional
GPS Navigator: Functional
```

---

## 5. Diagrama UML
El siguiente diagrama muestra la estructura del patrón implementado adaptado para este caso:

![Diagrama UML](https://github.com/user-attachments/assets/358e7e60-7f6b-43e1-9593-ce286d39d16f)

---

## 6. Explicación de la Implementación
El Patrón Builder permite construir objetos complejos paso a paso sin exponer detalles innecesarios de su implementación. En este proyecto, se usa para construir automóviles (**Car**) y sus manuales (**Manual**).

### **Interfaz Builder**
Define los métodos necesarios para configurar atributos como el tipo de auto, motor, transmisión, asientos, GPS, etc.

### **Clases `CarBuilder` y `CarManualBuilder`**
- `CarBuilder`: Implementa `Builder` para construir un objeto `Car`.
- `CarManualBuilder`: Implementa `Builder` para construir un objeto `Manual` con detalles del automóvil.

### **Clase Director**
- Define métodos para construir diferentes tipos de automóviles (`constructSportsCar`, `constructCityCar`, etc.), asegurando una secuencia válida de construcción.

### **Clase Demo**
- Usa `Director` para crear un automóvil deportivo con `CarBuilder`.
- Usa `Director` para generar su manual con `CarManualBuilder`.
- Imprime los resultados en consola.

Este diseño desacopla la lógica de construcción, facilita la reutilización de código y permite crear variaciones del producto sin afectar su estructura.
