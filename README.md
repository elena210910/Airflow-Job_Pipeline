# Airflow-Job_Pipeline

![](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/apache%20air.jpg)


## Objetivo del Proyecto
El objetivo es crear un pipeline que cargue los datos automáticamente una vez al día utilizando Apache Airflow.🚀 
Esto permitirá mantener los datos actualizados y disponibles para análisis continuos sin intervención manual.
Además, los datos finales serán cargados en AWS S3, asegurando que estén accesibles y almacenados de manera segura.


## Sobre los datos con los que vamos a trabajar

Descripción de los datos y su utilidad para el estudio
Este conjunto de datos contiene todas las solicitudes de trabajo presentadas a través de las oficinas de los distritos,
mediante eFiling o a través de HUB, que tienen una "Fecha de última acción" desde el 1 de enero de 2000. Este conjunto de datos no incluye trabajos presentados a través de DOB NOW.
[El enlace de la página web que proporciona los datos.](https://data.cityofnewyork.us/Housing-Development/DOB-Job-Application-Filings/ic3t-wcy2/about_data)

## Utilidad del estudio de estos datos

**Tendencias históricas:** Analizar las solicitudes de trabajo a lo largo del tiempo puede 
mostrar cómo han cambiado las tendencias en la industria de la construcción.

**Diferencias regionales:** Identificar cómo se distribuyen las solicitudes en diferentes distritos y oficinas.

**Tipos de proyectos:** Comparar las solicitudes por diferentes tipos de proyectos para identificar patrones predominantes.

**Velocidad de procesamiento de solicitudes:** Evaluar cuánto tiempo tarda en procesarse una solicitud y cómo ha cambiado esta velocidad.

**Patrones estacionales:** Identificar tendencias estacionales en la presentación de solicitudes, como picos en ciertos meses del año.




### ***Proceso de creación del pipeline***

- Verificación del [código](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/first_code_python) y acceso a la API: 
  Antes de crear el DAG, verifiqué el funcionamiento del código y la correcta conexión a la API
  para asegurarme de que los datos se obtuvieran correctamente.
  Los datos obtenidos a través del API vienen en formato JSON, pero como tienen una estructura organizada (cada objeto tiene las mismas claves),
  se pueden transformar fácilmente en un formato tabular utilizando pandas y un DataFrame.
  Esto me permite manejar y analizar los datos de manera más eficiente en un entorno de análisis estructurado.


RESULTADO OBTENIDO:

![](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/first_code.PNG)



- Creación del [DAG:](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/DAG_python) Basado en el código verificado, creé un DAG en Airflow para automatizar el proceso de carga 
  de datos.
  Guardado los datos en AWS S3: Una vez que los datos fueron guardados en AWS S3, verifiqué su disponibilidad y la integridad.


  
  RESUNTADO OBTENIDO:


  
  
  ![](https://github.com/user-attachments/assets/b9b02c38-67f6-40db-92b5-828767957273)




  ![](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/s3_dag.PNG)









  

  

  



- Acceso a los datos en S3: Después de guardar los datos en S3, utilicé biblioteca Dask para analizarlos y extraerlos desde S3.
  [Este código](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/result_code_python) es una demostración y verificación de que 
  nuestro DAG funciona correctamente, guardando y leyendo datos desde AWS S3 de manera exitosa. 🎯
  
   ***El codigo realiza las siguientes acciones:***

   ✅ Crea una sesión y cliente S3 utilizando las credenciales de AWS.

   ✅ Verifica si un archivo específico está disponible en un bucket S3.

   ✅ Lee el archivo Parquet desde S3 utilizando Dask.

   ✅ Muestra las primeras filas del DataFrame.

   ✅ Calcula y muestra el número de filas y columnas.

   ✅ Encuentra y cuenta los duplicados en el DataFrame.

  **Ahora, con los datos disponibles, es posible trabajar con ellos y realizar diferentes análisis analíticos.**

    ![](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/final_code.PNG)
  




