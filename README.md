# PPT-BI – Proyecto final de Inteligencia de Negocios

Este proyecto corresponde al **trabajo final del curso de Inteligencia de Negocios** del programa de Maestría en Analítica de Datos para la Inteligencia de Negocios.  
En él se diseña, implementa y documenta una **bodega de datos clínico-asistencial** para la organización ficticia **MediRed**, desde la definición conceptual hasta el consumo analítico en un dashboard de Power BI embebido en la web.

## Contenido de la página web

La página `index.html` es una web interactiva organizada por pestañas, que resume de forma estructurada todo el proceso del proyecto:

### 1. Contexto del proyecto

- Descripción de la organización MediRed y del problema de negocio a resolver.  
- Identificación de las fuentes de información (SIS_CITAS, SIS_FACTURA, SIS_RRHH) y sus dominios clínico-asistenciales y administrativos.  
- Alcance del proyecto, objetivos analíticos y visión general de la arquitectura de la solución.

### 2. Modelo dimensional y diseño del DW

- Definición de la **granularidad** de los hechos principales (citas, facturación, etc.).  
- Descripción de las **tablas de hechos** y **dimensiones** (DIM_MEDICO, DIM_PACIENTE, DIM_ESPECIALIDAD, DIM_TIEMPO, entre otras), incluyendo claves empresariales y claves sustitutas.  
- Presentación del **bus de datos (bus matrix)** que cruza procesos de negocio y dimensiones compartidas al estilo Kimball.

### 3. Implementación física en Oracle

- Especificación del DDL de las tablas del Data Warehouse en Oracle, alineado con el modelo dimensional.  
- Detalle de tipos de datos, restricciones de integridad y consideraciones de rendimiento para la carga de datos.  
- Ejemplos de estructuras clave como la tabla `DIM_MEDICO` y las tablas de hechos de citas y facturación.

### 4. Procesos ETL con Apache Hop

- Descripción de los pipelines desarrollados en Apache Hop para la carga de dimensiones y hechos.  
- Explicación de transformaciones de calidad de datos: operaciones de texto, reemplazo de nulos, generación de claves sustitutas, deduplicación y lookups entre flujos.  
- Referencia a los flujos específicos (por ejemplo, `P_DIM_MEDICO`) que integran archivos CSV de origen, reglas de negocio y salidas hacia Oracle.

### 5. Consultas SQL analíticas

- Conjunto de sentencias SQL sobre el DW que materializan indicadores clave de desempeño (KPIs).  
- Ejemplos de métricas como ocupación de agendas, productividad de médicos, análisis de facturación y comportamiento de citas.  
- Uso de funciones analíticas y filtros para validar la correcta consistencia de los datos cargados.

### 6. Dashboard de Power BI embebido

- Inclusión de un **dashboard interactivo de Power BI**, embebido mediante un iframe público dentro de la página.  
- El dashboard consume directamente el Data Warehouse construido y presenta los KPIs clínico-asistenciales y financieros definidos en el proyecto.  
- Esta sección cierra el flujo end-to-end: desde las fuentes operacionales, pasando por el DW y los procesos ETL, hasta la visualización final para soporte a la toma de decisiones.

---
