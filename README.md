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

Asimismo pudimos encontrar un dataset del gobierno de la ciudad de Buenos Aires en donde se encuentran las licencias emitidas por año. Con el podemos hacer algunos graficos para entender mejor la dinamica de de generos en la expedicion de licencia de conducir.


#PROVINCIA DE BUENOS AIRES#
Dentro del rango etario 18-50 años se expidió la mayor cantidad de licencias nacionales de conducir. En ese aspecto, de un total de 668.641, hubo 222.020 que correspondieron a personas de entre 18 y 30 años; 223.242 se destinaron a conductores y conductoras de entre 31 y 40 años; y 223.379 al rango etario 41-50 años.

Como contrapartida, la menor cantidad de licencias emitidas fue para menores de 18 años de edad (9.796) y mayores de 80 (21.573). En el medio se ubican los rangos 51-60 (160.547 licencias), 61-70 (96.224) y 71-80 (118.023).

En tanto, en cuanto a géneros, se emitieron 755.023 (70,2%) licencias para hombres y 319.767 (29,8%) para mujeres.
#CIUDAD DE BUENOS AIRES
Según los datos proporcionados por la Dirección General de Estadística y Censos del Gobierno de la Ciudad de Buenos Aires, la emisión de licencias de conducir en la Ciudad de Buenos Aires entre 2006 y 2023 refleja una marcada predominancia de los hombres sobre las mujeres en la obtención de licencias, tanto nuevas como renovadas. A continuación, se presentan los hallazgos más relevantes:

1. Distribución por Género
Predominio Masculino: Del total de licencias emitidas entre 2006 y 2023 (6.080.568), el 69.5% correspondió a hombres (4.309.751) y el 30.5% a mujeres (1.770.817). Esta brecha se mantiene tanto en licencias nuevas como renovadas.

Licencias Nuevas: De 1.020.004 licencias nuevas, el 65.9% fueron otorgadas a hombres (672.785) y el 34.1% a mujeres (347.219).

Licencias Renovadas: De 5.060.564 renovaciones, el 71.9% correspondió a hombres (3.636.966) y el 28.1% a mujeres (1.423.598).

2. Tendencias Temporales
Evolución Anual: La emisión de licencias ha experimentado fluctuaciones a lo largo de los años. Por ejemplo:

En 2006, se emitieron 280.062 licencias, con un 23.5% de licencias nuevas (70.720) y un 76.5% de renovaciones (209.342).

En 2020, debido a la pandemia de COVID-19, la emisión de licencias se redujo drásticamente a 101.424, con solo 13.187 licencias nuevas.

En 2023, se observa una recuperación, con 352.491 licencias emitidas hasta octubre, de las cuales 35.845 fueron nuevas.

3. Diferencias por Género en Licencias Nuevas y Renovadas
Licencias Nuevas: La proporción de mujeres que obtienen licencias nuevas ha aumentado ligeramente con el tiempo. Por ejemplo:

En 2006, las mujeres representaron el 33.2% de las licencias nuevas (23.471 de 70.720).

En 2023, esta proporción aumentó al 41.5% (14.866 de 35.845).

Licencias Renovadas: La brecha de género es más pronunciada en las renovaciones, donde las mujeres representan solo el 28.1% del total.

4. Meses con Mayor Actividad
Los meses de enero, marzo y septiembre suelen ser los de mayor emisión de licencias, coincidiendo con el inicio de ciclos lectivos y la preparación para la temporada de verano.

Por el contrario, los meses de febrero y abril registran una menor actividad, posiblemente debido a las vacaciones y festividades.

5. Impacto de la Pandemia (2020-2021)
La pandemia de COVID-19 tuvo un impacto significativo en la emisión de licencias:

En 2020, solo se emitieron 101.424 licencias, con una caída del 77.8% en comparación con 2019 (457.823).

En 2021, la recuperación fue lenta, con 76.210 licencias emitidas, de las cuales el 77.3% fueron renovaciones.

6. Comparación con Otras Jurisdicciones
Al igual que en la Provincia de Buenos Aires, donde el 70.2% de las licencias corresponden a hombres y el 29.8% a mujeres, la Ciudad de Buenos Aires refleja una tendencia similar, con una participación femenina ligeramente superior (30.5%).

7. Conclusiones
La conducción en la Ciudad de Buenos Aires continúa siendo una actividad predominantemente masculina, aunque la participación de mujeres ha aumentado en los últimos años, especialmente en la obtención de licencias nuevas.

La pandemia de COVID-19 tuvo un impacto significativo en la emisión de licencias, con una lenta recuperación en 2021 y 2022.

Estos datos refuerzan la necesidad de políticas públicas que fomenten la igualdad de género en el acceso a la movilidad y la seguridad vial.

