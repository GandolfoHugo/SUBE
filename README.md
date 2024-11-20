# UN ANALISIS DE DATOS DE MOVILIDAD EN TRANSPORTE PÚBLICO EN AMBA. (2020 - 2024)
## TENDENCIAS CRECIENTES Y GÉNERO 

Este es un breve análisis de los datos públicos publicados por el Ministerio de Transporte de la Nación. En este repositorio podrán encontrar tanto los datos en formato .csv como su respectivo análisis por año.

## Metodología

La metodología empleada en el análisis de movilidad con datos de SUBE se basa en la manipulación y visualización de datos a partir de un conjunto de datos en formato CSV descargados desde los Datasets de Datos Abiertos proporcionados por el Estado Nacional Argentino. Se utilizaron diferentes librerias en R utilizando Quarto obteniendo informes en HTTML para su reproduccion y mejoramiento a quien desee. A continuación, se describen los pasos realizados:

### Carga de Datos

1. **Carga de Librerías**: Se cargan las librerías necesarias para el análisis, incluyendo `tidyverse`, `ggplot2`, `lubridate`, entre otras, que facilitan la manipulación y visualización de los datos.

2. **Carga de la Base de Datos**: Se define una función `base_sube` que permite cargar los datos desde una URL específica. En este caso, se utiliza un archivo CSV que contiene información sobre los usuarios de SUBE desde el 2020 hasta el 2024.

### Filtrado y Agrupación

3. **Filtrado de Datos**: Se filtran los datos para obtener solo aquellos correspondientes al Área Metropolitana de Buenos Aires (AMBA) y se seleccionan los registros con totales de transporte.

4. **Agrupación por Género**: Se agrupan los datos por día y género, sumando la cantidad total de viajes para cada combinación. Se reemplazan los registros vacíos en la columna de género por "Sin registro".

5. **Agrupación por Día**: Se crea una base de datos que agrupa la cantidad total de viajes por día.

### Procesamiento de Fechas y Visualización

6. **Conversión de Formato de Fecha**: Se convierte la columna de fecha a un formato adecuado para su análisis y visualización.

7. **Visualización de la Serie Temporal**: Se utiliza `ggplot2` para graficar la movilidad diaria por género, mostrando la cantidad de viajes a lo largo del tiempo.

8. **Personalización de Gráficas**: Se añaden eventos relevantes (como el inicio del ciclo lectivo) y se personalizan las gráficas con colores específicos para cada género.

### Análisis de Descuentos

9. **Filtrado de Descuentos**: Se filtran los datos para excluir registros vacíos y se agrupan por motivo de descuento, sumando la cantidad total de viajes.

10. **Visualización de Descuentos**: Se crean gráficos de barras para visualizar la cantidad de viajes realizados con descuentos, diferenciando por género.

11. **Cálculo de Porcentajes**: Se transforman los valores absolutos en porcentajes para facilitar la interpretación de los datos.

### Promedios Mensuales

12. **Cálculo de Promedios Mensuales**: Se agrupan los datos por mes para calcular el promedio de viajes realizados, tanto en total como por género.

13. **Visualización de Promedios**: Se generan gráficos que muestran la cantidad promedio de viajes por mes, diferenciando entre hombres y mujeres.

### Interactividad

14. **Gráficos Interactivos**: Se utilizan funciones de `plotly` para crear gráficos interactivos que permiten explorar los datos de manera más dinámica.

### Conclusiones

Este análisis proporciona una visión detallada de la movilidad en el AMBA durante los años 2020 hasta el mes de Octubre del año 2024, permitiendo identificar patrones y tendencias en el uso del transporte público a través de la tarjeta SUBE.
Asimismo encontramos una tendencia de feminización en el transporte publico, secuencia repetida en todos los años analizados. Este analisis no posee la capacidad ni aspira a arriesgar soluciones posibles o hipotesis que expliquen adecuadamente(es decir, con la introduccion de variables de otros tipos para explicar correlaciones correctas). Aún así podemos moldear algunas posibles respuestas en base a totros datos publicos:

## DATOS DE INFORMES
Según el informe "Principales Indicadores de la Seguridad Via con Perspectiva de Género en Argentina" Marzo 2023 del Ministerio de Transporte
En Argentina, la conducción continúa siendo una actividad principalmente masculina. De las licencias de conducir emitidas en 2022 sólo el 31% corresponde a Mujeres frente al 69% de Varones.
En cuanto a las clases de licencias vigentes a la fecha, cabe mencionar que casi 3 de cada 10 licencias clase A 1 (motos) corresponde a una mujer, dato similar a la participación de las mujeres en las clases B de autos (35%). 






