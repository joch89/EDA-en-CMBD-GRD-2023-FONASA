# EDA-en-CMBD-GRD-2023-FONASA

Este documento de Colab realiza un análisis exploratorio de datos (EDA) sobre un conjunto de datos de egresos hospitalarios (GRD) del año 2023, obtenidos desde FONASA y con cambio de formato a .txt.  El análisis se divide en tres partes principales.

Dentro del archivo colab se encuentran los links, en google drive, a los archivos principales para ejecutar el código.

Parte 1: Carga, limpieza y descripción inicial. 

Se importan las bibliotecas necesarias (pandas, numpy, matplotlib, seaborn) y se carga el archivo CSV principal `GRD_PUBLICO_2023.csv`.  

Se realiza una exploración inicial de las columnas y tipos de datos. Luego se cruzan datos con archivos externos que corresponde a un archivo Excel con información sobre los hospitales y un archivo excel con las descripciones de los códigos GRD, agregando nuevas columnas al data frame principal con el nombre del hospital y la descripción del GRD, respectivamente. Se observa la cantidad de valores únicos en las columnas clave para entender la distribución de datos.

Parte 2: Análisis de valores nulos y ceros.

Se identifican y analizan las columnas con valores nulos o ceros, como `FECHA_NACIMIENTO`, `PROCEDIMIENTO1`, `IR_29301_COD_GRD`, y `SERVICIOALTA`.  

Se presentan las cantidades de valores faltantes y se propone una acción para cada caso (investigar, eliminar filas, etc.). Se genera un resumen en un dataframe con los problemas, cantidades y acciones propuestas. Este data frame se guarda posteriormente en un archivo Excel.

Parte 3: Eliminación de filas y creación de nuevas columnas. 

Se eliminan las filas con valores nulos en las columnas clave identificadas en la etapa anterior. Se crean nuevas columnas relevantes a partir de las existentes: `EDAD` (calculada desde la fecha de nacimiento), `ESTANCIA` (diferencia entre la fecha de alta y de ingreso), y `DESC` (descripción del GRD). 

Se realizan transformaciones en los tipos de datos de algunas columnas para asegurar consistencia y facilitar el análisis posterior. Los datos se guardan en un nuevo archivo CSV (`df_final.csv`). Finalmente, se filtra el dataset para un hospital en específico (Instituto de Neurocirugía Dr. Alfonso Asenjo) y se guarda este subconjunto en un archivo CSV (`df_hospital_eleccion.csv`).

Link al archivo final: https://drive.google.com/file/d/1599L_VEAGK24Pr-0VfGfCBwdRgrmVv0n/view?usp=sharing
