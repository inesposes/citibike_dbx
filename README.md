# Citi Bike – Proyecto de Ingeniería de Datos con Databricks

## 1. Descripción del proyecto

Proyecto de Ingeniería de Datos basado en la ingesta, transformación y modelado de datos reales del sistema de bicicletas compartidas **Citi Bike de Nueva York**.

El objetivo es construir un pipeline ELT de principio a fin utilizando Databricks, PySpark y Delta Lake, aplicando la arquitectura Medallion (Bronze, Silver y Gold).

A través de este proyecto se trabaja con datos reales para construir una plataforma de datos estructurada, escalable y preparada para su explotación analítica.

## 2. Objetivos

Los principales objetivos del proyecto son:

- Construir un pipeline ELT utilizando Databricks.
- Implementar la arquitectura Medallion (Bronze, Silver y Gold).
- Utilizar PySpark para el procesamiento y transformación de datos.
- Almacenar los datos utilizando Delta Lake.
- Aplicar reglas de limpieza y validación de datos.
- Diseñar un modelo dimensional para facilitar el análisis.
- Construir tablas de hechos y dimensiones.

## 3. Fuente de datos

El proyecto utiliza datos públicos del sistema Citi Bike, el servicio de bicicletas compartidas de Nueva York.

Los datos contienen información sobre los trayectos realizados por los usuarios, incluyendo:

- Fecha y hora de inicio y finalización del trayecto.
- Estaciones de origen y destino.
- Duración del trayecto.
- Identificador de la bicicleta.
- Tipo de usuario (miembro o usuario ocasional).
- Tipo de bicicleta.

**Fuente:** [Citi Bike System Data](https://citibikenyc.com/system-data)

Los datos se proporcionan mediante archivos descargables que se utilizan como fuente del proceso de ingesta.
## 4. Flujo de datos ELT
El procesamiento sigue las siguientes etapas:

1. **Ingesta:** carga de los archivos originales de Citi Bike en Bronze.
2. **Transformación:** limpieza, validación y enriquecimiento de los datos en Silver.
3. **Modelado:** construcción de tablas de hechos y dimensiones en Gold.
4. **Explotación:** consultas analíticas sobre el modelo final.

## 5. Modelo de datos – Gold

La capa Gold implementa un modelo dimensional orientado al análisis de los trayectos realizados por los usuarios.

### Tabla de hechos

| Tabla | Descripción |
|---|---|
| `fact_trips` | Información transaccional de cada trayecto realizado. |

### Tablas de dimensiones

| Tabla | Descripción |
|---|---|
| `dim_time` | Información temporal: año, mes, día, día de la semana y hora. |
| `dim_station` | Información de las estaciones de origen y destino. |
| `dim_bike` | Información relacionada con las bicicletas. |
| `dim_rider` | Clasificación de los usuarios según su tipo. |

El modelo permite analizar patrones de uso, comportamiento de los usuarios, actividad de las estaciones y tendencias temporales.

## 6. Tecnologías utilizadas

| Tecnología | Uso |
|---|---|
| Databricks | Plataforma de desarrollo y procesamiento de datos. |
| Apache Spark | Procesamiento distribuido. |
| PySpark | Transformación de datos mediante Python. |
| Delta Lake | Almacenamiento y gestión de tablas Delta. |
| Python | Lenguaje de programación. |
| SQL | Consultas y análisis de datos. |
| Git / GitHub | Control de versiones y documentación. |

## 7. Estructura del repositorio

```text
citibike-data-engineering/
│
├── README.md
│
├── 01_bronze/
│   └── ingestion.ipynb
│
├── 02_silver/
│   └── cleaning.ipynb
│
└── 03_gold
    └── gold_modelling.ipynb


```

## 8. Mejoras y próximos pasos

El proyecto contempla futuras mejoras para ampliar sus capacidades:

- Implementación de procesos de carga incremental.
- Orquestación del pipeline mediante Databricks Workflows.
- Incorporación de mecanismos de monitorización y logging.
- Desarrollo de dashboards para la visualización de indicadores.

## 11. Estado del proyecto

Proyecto en desarrollo.

El objetivo es construir progresivamente un pipeline ELT completo, incluyendo nuevas casuísticas y usando diferentes características de Databricks
