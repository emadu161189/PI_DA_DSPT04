# Proyecto Individual N° 2


# Telecomunicaciones


Este proyecto se centra en el análisis de datos en el sector de las telecomunicaciones argentino. Incluye un Análisis Exploratorio de Datos (EDA), un Dashboard interactivo y dos indicadores clave de rendimiento (KPIs) relevantes para el contexto.


# Contenido
•	EDA.ipynb: Archivo Jupyter Notebook que contiene el Análisis Exploratorio de Datos.
•	Dashboard Interactivo: Disponible en https://public.tableau.com/views/Dashboard_PI01_DA/Dashboard1?:language=es-ES&publish=yes&:display_count=n&:origin=viz_share_link
•	KPIs:
•	Kpi 1: Aumentar en un 2% el acceso al servicio de internet para el próximo trimestre, cada 100 hogares.
•	Kpi 2: Equiparar la velocidad promedio de bajada entre las 24 provincias de la Republica Argentina dentro de un rango de diferencia de ± 10 Mbps dentro de los próximos 5 años.
•	Datasets: Fuente https://datosabiertos.enacom.gob.ar/dashboards/20000/acceso-a-internet/


# Requisitos
El proyecto utiliza:
•	Python
•	Bibliotecas: Pandas, Numpy, Wordcloud, Matplotlib, Random, Re.
•	Tableau Public.


# Detalles del Proyecto
•	El Análisis Exploratorio de Datos abarca la carga de datos, limpieza, visualización de patrones y tendencias en datos de telecomunicaciones.


# Informe de Análisis Exploratorio de Datos:
Aspectos Generales: Se tomaron datos públicos y abiertos sobre acceso a internet en la Republica Argentina del sitio web oficial del ENACOM. Si bien los datos provistos por ENACOM accesibles a través de API u opción ‘Exportar’ se encuentran aceptablemente limpios, los mismos presentan incongruencias en todos los campos numéricos que expresan las cantidades de acceso a internet, los mismos con el aparente fin de redondearlos y trabajar con cifras mas pequeñas, fueron truncados en las unidades con peso mas alto sin llevar coherencia entre sí, por lo que se observan campos que contienen diferentes datos expresados en ‘unidades de mil’ y ‘unidades de millón’ generando una alteración relevante en el significado de los mismos. Debido a lo mencionado se opto en este trabajo procesar los datos accediendo a los archivos fuente desde los cuales obtuvo los mismos el ENACOM y trabajar con las cifras crudas.


# Primer dataset: ‘penetración de internet fijo por cada 100 hogares’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Provincia, Accesos por cada 100 hogares.
Se realiza la transformación a variable numérica a los datos cuantitativos, se obtienen las primeras 5 líneas de dataframe y se corrobora mediante la función Unique que los valores de las provincias sean 24 diferentes (total de provincias argentinas incluyendo la ciudad de buenos aires). 
Se grafica una nube de palabras en base al valor de acceso por cada 100 hogares, concluyendo que Capital Federal y Buenos Aires son las provincias con mayor acceso, pero evidenciando marcada desigualdad con el resto de estas (Acciones realizadas en general en todos los datasets)
Se analizan outliers de variable cuantitativa hallando un bajo porcentaje coincidente con la alta concentración de habitantes en un numero ínfimo de provincias, lo que logra en algunos casos mayor numero de conexiones a internet que hogares.
Se imprime un gráfico de líneas evidenciando la cantidad de conexiones cada 100 hogares por provincia a través del tiempo, marcando generalmente crecimiento en todas ellas.
Se imprime un grafico de barras con los promedios en todos los periodos de acceso a internet cada 100 habitantes en cada provincia, reconfirmando y evidenciando la desigualdad entre las mismas expresada en la nube de palabras.


# Segundo dataset: ‘penetración de internet fijo por cada 100 Habitantes’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Accesos por cada 100 hogares, Accesos por cada 100 Hab y Periodo (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets)
Se analizan outliers de variable cuantitativa hallando un bajo porcentaje coincidente con la alta concentración de habitantes en un numero ínfimo de provincias, lo que logra en algunos casos mayor número de conexiones a internet que hogares.
Se expresa en un gráfico de líneas la comparación entre las variables de accesos cada 100 hogares y cada 100 habitantes evidenciando correlación en las mismas.


# Tercer dataset: ‘Accesos a internet discriminados por banda ancha/angosta’
Entiéndase como banda ancha al internet con alta velocidad de transferencia de datos y como banda angosta al internet con baja velocidad de transferencia de datos.
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Banda ancha fija, Dial up (Tecnología de banda angosta), Total y Periodo (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets). Las variables cuantitativas están expresadas en ‘cantidad de conexiones’.
Se expresa en un gráfico de líneas a través del tiempo el total de accesos a internet a nivel nacional, evidenciando un constante crecimiento con un leve retroceso en el año 2019.
Se expresa en un grafico de barras apiladas a través del tiempo los porcentajes de cada tipo de conexión a nivel nacional, evidenciándose el impacto ínfimo que tiene en internet banda angosta desde el 2014.


# Cuarto dataset: ‘Accesos a internet discriminados por banda ancha/angosta por provincia’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Provincia, Banda ancha fija, Dial up (Tecnología de banda angosta), Total y Periodo (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets). Las variables cuantitativas están expresadas en ‘cantidad de conexiones’.
Se imprime grafico de línea a través del tiempo de total de conexiones a internet por cada provincia, evidenciando crecimiento general en todas ellas.
Se expresa en un gráfico de barras apiladas a través del tiempo los porcentajes de cada tipo de conexión por cada provincia, evidenciándose que, si bien hay alguna incidencia mayor de la banda angosta en algunas provincias, se concretó una marcada igualdad con el correr del tiempo.


# Quinto dataset: ‘Accesos a internet discriminados por tecnología trimestral a nivel nacional’
Expresa los accesos a internet discriminados por cada una de las tecnologías existentes del mismo.
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, ADSL, Cablemódem, Fibra óptica, Wireless, Otros, Total y Periodo (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets). Las variables cuantitativas están expresadas en ‘cantidad de conexiones’.
No se detectan outliers.
Se expresa un gráfico de líneas múltiples a través del tiempo evidenciando crecimiento en todas las tecnologías mencionadas, excepto en ADSL, la cual presenta reducción. Esta tecnología consistente en la asimetría entre velocidades de carga y descarga probablemente este considerándose obsoleta.


# Sexto dataset: ‘Accesos a internet discriminados por tecnología y provincia’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Provincia, ADSL, Cablemódem, Fibra óptica, Wireless, Otros, Total y Periodo (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets). Las variables cuantitativas están expresadas en ‘cantidad de conexiones’.
Se expresa en grafico de líneas múltiples a través del tiempo la cantidad de conexiones discriminadas por tecnología en cada provincia, al igual que a nivel nacional se observa disminución de ADSL, aumento de incidencia en los últimos dos años de fibra óptica, alta incidencia de otras tecnologías en provincias del interior.


# Séptimo dataset: ‘Velocidad media de bajada’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Mbps (Media de bajada) y Trimestre.1 (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets). 
Se analizan outliers, hallándose solo en los valores correspondiente a Capital Federal por su marcada diferencia con el resto de las provincias.
Se grafica en grafico de líneas a través del tiempo la evolución de la velocidad de bajada a nivel nacional, se observa crecimiento continuo y brusco en el último año


# Octavo dataset: ‘Velocidad media de bajada por provincia’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Provincia, Mbps (Media de bajada) y Trimestre.1 (Columna que expresa en texto el trimestre y el año correspondiente, presente en varios datasets). 
Al igual que en otros datasets, se presentan problemas de repeticiones de nombres de provincias por mal tipeado, se realizan correcciones hasta obtener 24 valores únicos en el campo ‘Provincia’.
Se expresa en grafico de líneas a través del tiempo la evolución de la velocidad de bajada en cada provincia, el crecimiento es coincidente en todas ellas como asi el aumento exponencial en el último año.
Se expresa en grafico de barras por cada provincia el promedio de velocidad de bajada en el ultimo año, nuevamente se observa marcada diferencia entre las mismas con evidente ventaja a favor de las provincias que presentan mayor concentración de habitantes.
A partir de esta observación, se propone como objetivo asemejar la velocidad de transferencia de datos del servicio de internet en todas las provincias de Argentina, proponiéndose como indicador clave de rendimiento (KPI) “Equiparar la velocidad promedio de bajada entre las 24 provincias de la República Argentina dentro de un rango de diferencia de ± 10 Mbps dentro de los próximos 5 años”, considerando que el mismo cumpla las características de kpi:
•	Alcanzable: Los objetivos planteados deben de ser realistas.
•	Medible: Aunque suene obvio, un KPI debe de poder medirse.
•	Relevante: No te llenes de datos, selecciona solo los más importantes.
•	Periódico: El indicador tiene que ser analizable periódicamente.


# Noveno dataset: ‘Distribución de accesos a internet por rangos de velocidad’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, y distintos rangos de velocidad agrupados entre 512 Kbps y más de 30 Kbps.
Se grafica un grafico de barras apiladas expresando la distribución de los accesos por rango de velocidad a nivel nacional con una fuerte prevalencia de velocidades altas en los últimos periodos.


# Decimo dataset: ‘Distribución de accesos a internet por rangos de velocidad por provincia’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Provincia, y distintos rangos de velocidad agrupados entre 512 Kbps y más de 30 Kbps.
Se grafica en gráficos de barras apiladas expresando la distribución de los accesos por rango de velocidad por cada provincia, al igual que a nivel nacional, con una marcada prevalencia de velocidades altas en los últimos periodos.


# Onceavo dataset: ‘Acceso a internet por velocidad y provincia sin rangos’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Provincia, y distintos rangos de velocidad agrupados entre 0 y 10000 Mbps.
Se grafica en gráficos de líneas los promedios de velocidad de internet en cada provincia, arrojando datos crecientes en todas ellas excepto en Capital Federal donde marca una curiosa disminución.


# Doceavo dataset: ‘Ingresos trimestrales por servicios de internet’
Archivo CSV que contiene las siguientes columnas: Año, Trimestre, Ingresos y periodo (Expresión coloquial de trimestre-año)
Se observa aumento de los ingresos a través del tiempo, dado que Argentina se encuentra sumergida en un contexto económico inflacionario se considera este hecho como un resultado normal, de suma importancia monitorear el mismo.


# Treceavo dataset: ‘Acceso a internet fijo por velocidad de bajada y localidad’
Dataset con datos actuales de velocidad de internet sin incidencia del tiempo segmentado por localidades de cada provincia en todo el país.
Se omite análisis de Capital Federal ya que al poseer una sola localidad es redundante su análisis.
Se grafica en histograma la distribución por localidades de velocidad en cada provincia marcándose la media de velocidad en cada uno, en línea con lo que ocurre a nivel nacional, dentro de cada provincia existe una alta desigualdad de calidad de servicio entre sus localidades evidente en los marcados sesgos de cada gráfico.


# Catorceavo dataset: ‘Acceso a internet fijo tecnología y localidad’
Dataset con datos actuales de tecnologías de internet sin incidencia del tiempo segmentado por localidades de cada provincia en todo el país.
Se omite análisis de Capital Federal ya que al poseer una sola localidad es redundante su análisis.
Expresa en grafico de barras la incidencia de cada tecnología por provincia, basado en la cantidad de localidades que dispone de cada una. Se observa una alta incidencia de la tecnología ‘Satelital’ en todas las provincias, mas marcada en las consideradas provincias del interior del país.


# El Quinceavo dataset es redundante con el 14
•	El Dashboard interactivo proporciona una vista dinámica y filtrable de los datos relevantes para la toma de decisiones.


El Dashboard proporciona una vista interactiva de datos relevantes para el seguimiento de Kpis y datos considerados importantes para el monitoreo del sector telecomunicaciones.


# Autor
•	Emanuel Duenk
•	Contacto: eduenk@outlook.com.ar

