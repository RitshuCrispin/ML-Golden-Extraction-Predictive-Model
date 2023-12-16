# ML-Golden-Extraction-Predictive-Model
Prototipo de modelo ML para predecir la extracción de oro del mineral bruto. Para encontrar el mejor modelo se aplicó la técnica de Cross-Validation para los modelos Decision Tree Regressor, Random Forest Regressor y Linear Regressor.

# Descripcion del proyecto <a id='project_description'></a>
Prepara un prototipo de un modelo de machine learning para Zyfra. La empresa desarrolla soluciones de eficiencia para la industria pesada.
Los datos se almacenan en tres archivos:

- `gold_recovery_train.csv` — el dataset de entrenamiento 
- `gold_recovery_test.csv` —el dataset de prueba 
- `gold_recovery_full.csv` — el dataset fuente 

Los datos se indexan con la fecha y la hora de adquisición (`date`). Los parámetros cercanos en el tiempo suelen ser similares.

Algunos parámetros no están disponibles porque fueron medidos o calculados mucho más tarde. Por eso, algunas de las características que están presentes en el conjunto de entrenamiento pueden estar ausentes en el conjunto de prueba. El conjunto de prueba tampoco contiene objetivos.

El dataset fuente contiene los conjuntos de entrenamiento y prueba con todas las características.

Tienes a tu disposición los datos en bruto que solamente fueron descargados del almacén de datos. Antes de construir el modelo, comprueba que los datos sean correctos. Para ello, utiliza nuestras instrucciones.

## Objetivo <a id='objective'></a>

El modelo debe predecir la cantidad de oro extraído del mineral de oro. Dispones de los datos de extracción y purificación.

El modelo ayudará a optimizar la producción y a eliminar los parámetros no rentables.

Tendrás que:

1. preparar los datos;
2. realizar el análisis de datos;
3. desarrollar un modelo y entrenarlo.


# Conclusiones <a id='end'></a>

1. En la etapa de inicializacion del proyecto, se revisaron los 3 datasets entregados donde se encontraron algunas observaciones respecto a valores ausentes en todos los datasets y cantidad de columnas en el de prueba. Estos puntos fueron tratados en la etapa de procesamiento donde se tomo la decision de eliminar los valores ausentes con el proposito de mantener integros los datos y asi evitar la propagacion de errores.
2. En la etapa de analisis, se valido la distribucion de las concentraciones de los metales de oro, plata y plomo en diferentes etapas de proceso y concentracion, siendo el oro el que tiene mayores valores.
3. Seguidamente, en la preparacion de datos se definieron las variables objetivos que eran 2 y caracteristicas, ademas, se homologo las columnas faltantes en el conjunto de prueba y se creo la funcion para el calculo del error medio absoluto simetrico.
4. Se aplico la tecnica de validacion cruzada para encontrar el mejor modelo e hiperparametro de entrenamiento, pasando por decision tree regressor, random forest regressor y lineal regressor. El mejor resultado de exactitud y sMAPE se encontro en el modelo random forest regressor con 100 estimadores.
5. Por ultimo, se entreno nuevamente el modelo (sin validacion cruzada) en el conjunto de pruebas y luego paso por el conjunto de pruebas dandonos el valor de exactitud en ambos conjuntos: 96%.
6. Finalmente, el modelo predice que la recuperacion final de oro extraido sera:
    - En la etapa de flotacion, la concentracion de oro recuperado se predice ser de 87%.
    - En la etapa final, la concentracion de oro recuperado se predice ser de 69%. 

![Dispersion de predicciones de rougher recovery](https://github.com/RitshuCrispin/ML-Golden-Extraction-Predictive-Model/assets/130596539/7ba25aa9-8914-4369-8de4-d790237aeaba)

![Dispersion de predicciones de final recovery](https://github.com/RitshuCrispin/ML-Golden-Extraction-Predictive-Model/assets/130596539/e5845b05-ec10-412c-abaf-dbc8e019b453)
