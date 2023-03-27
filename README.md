### scientific_role
# Introducción
Se presenta todo el flujo para la generación de un modelo que tenga la capacidad de predecir la probailidad de pago de un usuario. Se crea un producto simulando un posible escenario donde el modelo es necesario desplegarlo, re entrenarlo, ajustar parámetros y otro.
## Contenido:
El proyecto se encuentra conformado por los siguientes archivos:
 - data_exploration.ipynb: En este archivo se realiza el análisis descriptivo de algunas variables.
 - variable_analysis.ipynb: En este archivo se realiza un análisis de la calidad de los datos y algunos métodos de selección de variables. En este archivo también se concluyen sobre algunas estrategias en la creación de algunas variables que le den valor al modelo.
  - clean_data.py: En este archivo se limpia los datos garantizando la estructura de las variables. Como se menciono, el proyecto se realizó simulando una ejecución real, es por esto que este procedimiento se realiza en primer lugar simulando la comunicación con una base de datos que en muchas ocasiones la calidad de los datos no puede ser garantizada.
  - fixture_engineer.py: Este archivo se relaciona con el análisis realizado en variable_analysis.ipynb. En este se realiza la creación de algunas variables y la eliminación de algunas por altos valores de correlación.
  - preprocess_data.py: En este archivo se realiza el procesamiento de los datos antes de evaluarlos en diferentes modelos, en este realiza: Eliminación de outliers que disminuya la capacidad de generalizar, transformaciones de las variables continuas para evitar que altos valores tomen diferentes pesos en los parámetros de los modelos, balanceo de la base de datos de entrenamiento utilizando submuestreo de la clase mayoritaria y transformaciones de la base de datos de evaluación con los parámetros de las transformaciones del entrenamiento.
  - train_model.py: En este se evaluan 4 modelos: RandomForestClassifier, lightgradientboost, Gradient Boosting classifier y Support vector machine. Se utiliza una grilla de parámetros para encontrar la mejor combinación y se fija un hiperparámetro de validación cruzada igual a 3. La métrica con la que se juzga y se optimiza es el "accuracy" que me permite minimizar los falsos positivos.

El código fue estructurado de manera que sea fácilmente editable en caso de presentar de detectar alguna falla o si se desea realizar un cambio en algunas estrategia de modelo.
