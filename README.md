<br>
<h1 align='center'>
 <b> :construction: Siniestros Viales :construction:</b>
</h1>


<br>
<p align='center'>
<img src = 'https://static.lajornadaestadodemexico.com/wp-content/uploads/2022/08/Siniestros-viales.jpg' height = 500>
<p>
<br>
  
## Índice

* [Propuesta y Objetivos](#memo-propuesta-y-objetivos)

* [Datos](#memo-datos)

* [ETL](#etl)

* [EDA](#bar_chart-eda)

* [Dashboard](#bar_chart-dashboard)
  
* [Desarrollo de KPIs](#bar_chart-desarrollo-de-kpis)


<br>

## :memo: Propuesta y Objetivos

El Observatorio de Movilidad y Seguridad Vial (OMSV), centro de estudios que se encuentra bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires, nos solicita la elaboración de un proyecto de anális de datos, con el fin de generar información que le permita a las autoridades locales tomar medidas para disminuir la cantidad de víctimas fatales de los siniestros viales.
Para ello disponemos de la informacion sobre siniestros viales en la ciudad de Buenos Aires del periodo 2016-2021.
Nuestros objetivos seran:

* Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

* Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

* Reducir en un 10% la cantidad de accidentes mortales de peatones en el último año, en CABA, respecto al año anterior.

<br>

## :memo: Datos

El DataSet proporcionado es:

* **homicidios.xlsx** 



La información detallada se encuentra en el [Diccionario de datos - Siniestros Viales](https://github.com/Malggan/Siniestros_viales/blob/6ac3f0870f3b3d3e9bed0766d696d4dbe9b8eafb/Datasets/Diccionario%20de%20datos%20Siniestros%20viales.xlsx).

<br>

## ETL

Se realizó la extracción, transformación y carga (ETL) del conjunto de datos entregado. El conjunto de datos se encontraban incompletos, por lo que aplicaron distintas estrategias para transformar las claves y completar campos incompletos con la moda del conjunto de datos. Luego se rellenaron algunos nulos de variables necesarias para el proyecto, se borraron columnas con muchos nulos o que no eran necesarias para el objetivo y se realizó una limpieza en campos que eran esenciales para los KPI requeridos.

Los detalles del ETL se puede ver en: 
+ [ETL Siniestros viales](https://github.com/Malggan/Siniestros_viales/blob/6ac3f0870f3b3d3e9bed0766d696d4dbe9b8eafb/ETL.ipynb) 

<br>


## :bar_chart: EDA

Se realizó el EDA al conjunto de datos sometido a ETL con el objetivo de identificar las variables que se pueden utilizar en el dashboard. Para ello se utilizó la librería Pandas para la manipulación de los datos y las librerías Matplotlib, Geopandas, contextily y Seaborn para la visualización de los graficos y mapas.

<br>

<p align="center">
<img src="https://github.com/Malggan/Siniestros_viales/blob/ed7b64385fb5c788f937b108655a79635184bc07/Images/Mapa%20EDA.png" alt="imagen de gráfico" width="400" height="500">
</p>
<p align="center">
<i>Mapa de comunas</i>
</p>

<br>


El desarrollo de este análisis se encuentra en: 
+ [EDA](https://github.com/Malggan/Siniestros_viales/blob/ed7b64385fb5c788f937b108655a79635184bc07/EDA.ipynb)


<br>

## :bar_chart: Dashboard

<p align="center">
<img src="https://github.com/Malggan/Siniestros_viales/blob/aa2c869bf24ea460ac3eaf07f060df4bb563db30/Images/DB.png?raw=true" alt="fastapi" width="700" height="380">
</p>
<p align="center">
<i>Dashoboard</i>
</p>

<br>

## :bar_chart: Desarrollo de KPIs


* **Semestral**: Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.
Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Se define como Tasa de homicidios en siniestros viales al número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, 
en este caso se toman 6 meses.
En este caso, para el año 2021, la Tasa de homicidios en siniestros viales fue de 1.77 lo que significa que, durante los primeros 6 meses del año 2021, hubo aproximadamente 1.77 homicidios en accidentes de tránsito por cada 100,000 habitantes. Ahora, el objetivo planteado es reducir esta tasa para el siguiente semestre de 2021 en un 10%, esto es 1.60. Cuando se calcula el KPI para este período se obtiene que la Tasa de homicidios en siniestros viales fue de 1.35, lo que significa que para el segundo semestre de 2021 se cumple con el objetivo propuesto.

* **Motocicletas**: Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.
Como se vio en el análisis exploratorio, el 42% de las víctimas mortales se transportaban en moto al momento del hecho, por lo que se consideró importante proponer el monitoreo de la cantidad de accidentes mortales en este tipo de conductor. Para ello se define a la Cantidad de accidentes mortales de motociclistas como el número absoluto de accidentes fatales en los que estuvieron nvolucradas víctimas que viajaban en moto en un determinado periodo temporal.
Para este caso, se toma como año actual al año 2021 y como año anterior al año 2020. En primer lugar, se calculó la Cantidad de accidentes mortales de motociclistas para el año 2020, el cual resultó de 26, de esta manera el objetivo a cumplir es de 24.18 (es decir, la reducción del 7% de la cantidad de accidentes para 2020). El calcular la Cantidad de accidentes mortales de motociclistas para el año 2021 resultó de 64.29 lo que significa que aumentó un 76.92% la cantidad de muertes de conductores de motociclistas respecto del 2021.

* **Peatones**: Reducir en un 10% la cantidad de accidentes mortales de peatones en el último año, en CABA, respecto al año anterior.


<br>

<p align="center">
<img src="https://github.com/Malggan/Siniestros_viales/blob/aa2c869bf24ea460ac3eaf07f060df4bb563db30/Images/KPI.png?raw=true" alt="fastapi" width="700" height="380">
</p>
<p align="center">
<i>Muestra KPIS</i>
</p>

<br>
