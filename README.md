# Proyecto Individual 2 Datathon
Usted ha sido contactado para el área de Machine Learning de una importante empresa inversora dentro del rubro de la inmobiliaria en Estados Unidos.​El Team Lider le propone dos predicciones posibles, de las cuales puede elegir cuál realizar (o ambas si así lo quiere):​

1. Implementar un modelo de clasificación con aprendizaje supervisado que permita clasificar el precio de las propiedades en venta, utilizando los datos que se han puesto a su disposición.​Para esto debe crear la columna category_price, en la cual se consideran las categorías
* 'low': Para precios entre 0 y 999 dólares (debe tomar valor 1 en el archivo con las predicciones).
* 'medium': Para precios entre 1000 y 1999 dólares (debe tomar valor 0 en el archivo con las predicciones).
* 'high': Para precios desde 2000 dólares en adelante (debe tomar valor 0 en el archivo con las predicciones).​Considerando esta categorización, el objetivo es predecir si una propiedad pertenece a la categoría de precios bajos (low).​
2. Implementar un modelo de clasificación con aprendizaje no supervisado, utilizando clustering que agrupe las propiedades por segun las 3 categorias a las que pueden pertenecer. Para ello, solo usaran el dataset de test provisto, eliminando previamente las caracteristicas que presenten nulos.​

# Desarrollo del proyecto
1. Análisis exploratorio de los datos (EDA)
* Carga del dataset en formato parquet utilizando pandas y pyarrow
* Exploración de tipos de variables, valores nulos y repetidos
* Exploración de los estadísticos principales del dataset
* Segmentación de la columna price en las categorías 'low', 'medium' y 'high'
* Conversión de variables categóricas a códigos numéricos
* Detección de outliers en las columnas sqfeet, beds y baths a través del análisis de histogramas, diagrama de cajas y bigotes y el test de Tukey. Se consideró el valor atípico el que se encuentra 1.5 veces la distancia al cuartil Q1 y al cuartil Q3  
* Se eliminan los outliers del dataset 
* Se realiza un análisis de correlación entre las variables para obtener redundancia de características
* Se seleccionan las características que aportan al modelamiento

2. Modelamiento
* Se implementa un pipeline que automatiza el siguiente flujo de trabajo:
- escalamiento de los datos con StandardScaler que estandariza las características con media cero y varianza 1
- Reducción de dimensionalidad utilizando PCA con 6 componentes 
- Implementación de 4 modelos de clasificación 

* Modelos de clasificación implementados
- GradientBoostingClassifier
- DecisionTreeClassifier
- XGBClassifier
- RandomForestClassifier

![Accuracy]()



