Implementación del Patrón Builder

El Patrón Builder es un patrón de diseño creacional que permite construir objetos complejos paso a paso, separando su construcción de su representación final.
📌 Características principales:
Facilita la creación de objetos con múltiples configuraciones.
Evita constructores con demasiados parámetros.
Permite construir diferentes representaciones del mismo objeto sin duplicar código.
Estructura del Proyecto
La estructura del proyecto sigue el estándar de Maven:

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
    │   └── resources      # Recursos adicionales
    └── test
    

Instrucciones de Instalación
Clonar el repositorio:
git clone [https://github.com/usuario/nombre_repositorio.git](https://github.com/JuanBenitez21/Patron_Builder.git)
cd Patron_Builder
Compilar el proyecto:
mvn clean compile
Ejecutar el proyecto:
mvn exec:java -Dexec.mainClass="director.Demo"
Ejemplo de Ejecución
Al ejecutar el programa, deberías ver la siguiente salida:

Car built:
SPORTS_CAR
Car manual built:
Type of car: SPORTS_CAR
Count of seats: 2
Engine: volume - 3.0; mileage - 0.0
Transmission: SEMI_AUTOMATIC
Trip Computer: Functional
GPS Navigator: Functional

Diagrama UML
El siguiente diagrama muestra la estructura del patrón implementado:



Diagrama UML

<img width="739" alt="Captura de pantalla 2025-02-24 a la(s) 2 51 07 p m" src="https://github.com/user-attachments/assets/358e7e60-7f6b-43e1-9593-ce286d39d16f" />


Explicación de la Implementación
El Patrón Builder permite construir objetos complejos paso a paso sin exponer detalles innecesarios de su implementación. En este proyecto, se usa para construir automóviles (Car) y sus manuales (Manual).

Interfaz Builder
Define los métodos necesarios para configurar atributos como el tipo de auto, motor, transmisión, asientos, GPS, etc.
Clases CarBuilder y CarManualBuilder
CarBuilder: Implementa Builder para construir un objeto Car.
CarManualBuilder: Implementa Builder para construir un objeto Manual con detalles del automóvil.
Clase Director
Define métodos para construir diferentes tipos de automóviles (constructSportsCar, constructCityCar, etc.), asegurando una secuencia válida de construcción.
Clase Demo
Usa Director para crear un automóvil deportivo con CarBuilder.
Usa Director para generar su manual con CarManualBuilder.
Imprime los resultados en consola.
Este diseño desacopla la lógica de construcción, facilita la reutilización de código y permite crear variaciones del producto sin afectar su estructura.

Contribuciones
Este proyecto fue desarrollado por: - Juan Pablo Benitez Bernal - Mariana Valle


