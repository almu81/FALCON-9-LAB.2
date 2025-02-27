# FALCON-9-LAB.2
Markdown

# Predicción de Aterrizaje de la Primera Etapa del SpaceX Falcon 9 - Lab 1: Recolección de Datos

Este proyecto tiene como objetivo predecir si la primera etapa del Falcon 9 de SpaceX aterrizará con éxito. SpaceX anuncia lanzamientos de cohetes Falcon 9 en su sitio web a un costo de 62 millones de dólares; otros proveedores cuestan más de 165 millones de dólares cada uno, gran parte del ahorro se debe a que SpaceX puede reutilizar la primera etapa. Por lo tanto, si podemos determinar si la primera etapa aterrizará, podemos determinar el costo de un lanzamiento. Esta información puede ser utilizada si una empresa alternativa quiere competir contra SpaceX por un lanzamiento de cohetes. En este laboratorio, recolectaremos y nos aseguraremos de que los datos estén en el formato correcto desde una API.

## Objetivos

En este laboratorio, realizarás una solicitud GET a la API de SpaceX. También realizarás algunas manipulaciones y formateos básicos de datos.

* Solicitud a la API de SpaceX
* Limpieza de los datos solicitados

## Habilidades clave demostradas

* **Extracción de Datos de APIs:** Obtención de datos estructurados JSON desde la API de SpaceX usando Requests.
* **Limpieza y Procesamiento de Datos:** Manejo de datos anidados y listas, formateo de fechas, extracción de información relevante usando Pandas.
* **Análisis de Datos:** Creación de DataFrames, filtrado de datos, manejo de valores nulos, manipulación de datos para análisis.
* **Preparación de Datos para Modelado:** Creación de un dataset limpio y estructurado para futuros modelos de predicción.
* **Manejo de valores nulos:** imputación de datos faltantes en la columna `PayloadMass`, y manejo correcto de los datos faltantes en `LandingPad`.
* **Exportación de datos:** guardado de los datos procesados en un archivo CSV (`dataset_part_1.csv`).

## Tecnologías utilizadas

* Python
* Pandas
* Requests
* NumPy

## Instrucciones breves

Requisitos: `pip install requests pandas numpy`

## Pasos Realizados

1.  **Importación de Librerías y Definición de Funciones Auxiliares:**
    * Se importaron las bibliotecas necesarias: `requests`, `pandas`, `numpy`, `datetime`.
    * Se definieron funciones auxiliares (`getBoosterVersion`, `getLaunchSite`, `getPayloadData`, `getCoreData`) para extraer información de la API de SpaceX.

2.  **Solicitud y Análisis de Datos de la API de SpaceX:**
    * Se realizó una solicitud GET a la API de SpaceX usando una URL estática.
    * Se convirtió la respuesta JSON a un DataFrame de Pandas usando `json_normalize`.
    * Se seleccionó un subconjunto de columnas relevantes y se filtraron los datos.
    * Se extrajeron datos específicos de las columnas `rocket`, `payloads`, `launchpad`, y `cores` usando las funciones auxiliares y la API.

3.  **Construcción del Dataset:**
    * Se creó un diccionario con los datos extraídos.
    * Se creó un DataFrame de Pandas a partir del diccionario.

4.  **Filtrado de Lanzamientos de Falcon 9:**
    * Se filtraron los datos para incluir solo lanzamientos de Falcon 9.
    * Se reseteó la columna `FlightNumber` para asegurar una secuencia correcta.

5.  **Manejo de Valores Nulos:**
    * Se verificaron los valores nulos en el DataFrame.
    * Se imputaron los valores nulos en la columna `PayloadMass` con la media.
    * Se mantuvieron los valores nulos en la columna `LandingPad` para representar los casos en que no se utilizó una plataforma de aterrizaje.

6.  **Exportación del Dataset:**
    * El DataFrame limpio se exportó a un archivo CSV llamado `dataset_part_2.csv`.

## Desafíos y soluciones

* **Manejo de datos anidados y listas:** Se utilizaron funciones de Pandas para extraer y aplanar los datos.
* **Extracción y formateo correcto de fechas:** Se implementaron funciones de Pandas para convertir y formatear las fechas.
* **Manejo de valores nulos:** Se imputaron los valores nulos en `PayloadMass` con la media y se manejaron los valores nulos en `LandingPad` correctamente.
* **Filtrado de datos:** Se filtraron los datos para incluir solo lanzamientos de Falcon 9.

## Posibles mejoras

* Realizar análisis exploratorio de datos (EDA) más profundo.
* Desarrollar modelos de machine learning para predecir resultados de lanzamientos.
* Añadir visualizaciones de datos usando Matplotlib o Seaborn.
* Integrar datos de otras fuentes para enriquecer el dataset.
