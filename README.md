# modern_bigdata_architectures
Soluciones desarrolladas para la evaluación de la semana 4 del curso Fundamentos del Big Data, de la Especialización en Big Data y Analítica de Datos. El enfoque principal está en el diseño de arquitecturas modernas aplicadas a diferentes escenarios reales de negocio, abordando necesidades de escalabilidad, procesamiento en tiempo real y descentralización de datos.

## Contenido:

### 1. Escalabilidad en una fintech 
Se analiza el caso de una empresa del sector financiero que enfrenta una saturación de su servidor principal debido al crecimiento de usuarios. 
Se propone una solución escalable, explicando el tipo de escalabilidad más adecuada en términos de costo, rendimiento y disponibilidad. 
Se incluyen diagramas de la arquitectura actual y la recomendada.

### 2. Comparación entre arquitecturas Lambda, Kappa y Delta:
En este apartado se recomienda un patrón arquitectónico para una empresa de logística que necesita combinar procesamiento en tiempo real con reportes históricos.
La propuesta justifica la elección de una arquitectura basada en requerimientos de latencia, precisión, consistencia, mantenimiento y unificación de capas de datos.

Como arquitecto de datos, ¿qué patrón arquitectónico recomendarías: ¿Lambda, Kappa o Delta? Justifica tu elección según:

De acuerdo a las condiciones del caso comparativo recomendaría la arquitectura Kappa.

a. Las características de latencia, precisión y consistencia requeridas.

Esta arquitectura está diseñada para procesamiento en tiempo real, lo que permite hacer seguimiento a los movimientos de los vehículos de forma inmediata. Los datos históricos pueden almacenarse en un sistema distribuido sin necesidad de duplicación de pipelines.
La arquitectura Kappa proporciona baja latencia para análisis en tiempo real a diferencia de Lambda que, aunque permite las dos tareas puede verse afectada la precisión y la latencia. En cuanto al almacenamiento centralizado para consultas históricas la arquitectura Kappa cumple con esta tarea a diferencia de la arquitectura Delta la cual no es óptima para procesamiento inmediato de eventos.

b. La complejidad operativa del sistema y el mantenimiento del código.

De las 3 arquitecturas analizadas, la arquitectura Kappa ofrece menor complejidad operativa y por ende permite optimizar el mantenimiento y los costos de funcionamiento. Lo anterior debido a que cuenta con un único flujo de datos, reduciendo la gestión de código. 

c. La posibilidad de unificar almacenamiento o mantener diferentes capas.

Con la arquitectura Kappa se puede unificar almacenamiento y procesamiento en una sola fuente de datos a diferencia de las otras arquitecturas que requieren duplicidad de almacenamiento y por su estructura tienen diferentes capas.

d. Las ventajas que tu propuesta ofrece frente a las otras dos arquitecturas.

Ventajas:
- Sin duplicación de pipelines
- Reduce la carga operativa
- Procesamiento y precisión en reportes históricos
- Arquitectura sencilla
Lo anterior facilita el cumplimiento de los requerimientos de una empresa de logística internacional para gestionar sus datos.


e. Una breve descripción de cómo implementarías la solución, mencionando las capas o componentes principales.

1. Ingesta de datos
	Uso de Apache Kafka para capturar eventos de ubicación GPS y tráfico en tiempo real.
	Integración con sensores IoT en los vehículos.

2. Procesamiento de datos
	Apache Flink o Spark Streaming** para análisis en tiempo real
	Cálculo de métricas como velocidad, rutas óptimas y congestión de tráfico.

3. Almacenamiento
	Apache Cassandra o PostgreSQL** para almacenamiento persistente y consultas de reportes históricos.

4. Dashboard y reporting
	Grafana o Tableau para la visualización de KPIs de desempeño semanal y mensual.

5. Gestión de datos históricos
	Acceso a registros históricos sin necesidad de duplicación, aprovechando el almacenamiento distribuido.



### 3. Aplicación del enfoque Data Mesh:
Se aborda un caso en el que una empresa con más de 100 equipos busca evitar cuellos de botella en el equipo central de datos. 
Se presenta una propuesta basada en el enfoque Data Mesh, explicando cómo cada uno de sus principios (como ownership y data as a product) ayudan a resolver el problema. 
Además, se diseña una arquitectura basada en tecnologías actuales como AWS, Databricks y Azure.

## Herramientas utilizadas

- [draw.io](https://app.diagrams.net) para la creación de los diagramas arquitectónicos.
- Documentación oficial de AWS, Azure y Databricks para referencias y modelos de arquitectura.
- Conocimientos adquiridos durante la sesión de clases en vivo.

