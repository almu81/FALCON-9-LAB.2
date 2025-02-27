# FALCON-9-LAB.2
# Predicción del Aterrizaje de la Primera Etapa del Falcon 9 de SpaceX

Este repositorio contiene el código y los datos utilizados para predecir el resultado del aterrizaje de la primera etapa del Falcon 9 de SpaceX. El objetivo principal es clasificar los lanzamientos en función de si la primera etapa aterrizó con éxito o no.

## Descripción General

Este laboratorio se centra en la preparación y limpieza de datos, así como en la creación de una variable de clasificación (`Class`) basada en el resultado del lanzamiento (`Outcome`). Se utiliza un conjunto de datos que incluye información sobre los lanzamientos del Falcon 9, y se crea una variable binaria donde:

-   `Class = 0` indica un resultado de aterrizaje fallido (bad_outcome).
-   `Class = 1` indica un resultado de aterrizaje exitoso.

## Pasos Realizados

1.  **Creación de la Variable de Clasificación (`Class`):**
    -   Se define una lista `landing_class` basada en la columna `Outcome`.
    -   Si el `Outcome` está en el conjunto `bad_outcome`, `landing_class` es 0; de lo contrario, es 1.
    -   Esta lista se asigna a la columna `Class` del DataFrame.

2.  **Visualización de los Datos:**
    -   Se visualizan las primeras 5 filas del DataFrame para verificar la estructura y los datos.
    -   Se visualizan las primeras 8 filas de la columna `Class` para confirmar la correcta creación de la variable de clasificación.

3.  **Cálculo de la Tasa de Éxito:**
    -   Se calcula la media de la columna `Class` para determinar la tasa de éxito general de los aterrizajes.

4.  **Exportación de Datos:**
    -   El DataFrame resultante se exporta a un archivo CSV llamado `dataset_part_2.csv` para su uso en el siguiente laboratorio.

## Código

El código principal se encuentra en un cuaderno de Jupyter Notebook. Los pasos clave incluyen:

```python
# landing_class = 0 if bad_outcome
# landing_class = 1 otherwise

df['Class'] = landing_class
df[['Class']].head(8)

df.head(5)

df["Class"].mean()

df.to_csv("dataset_part_2.csv", index=False)
