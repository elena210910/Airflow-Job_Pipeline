# Airflow-Job_Pipeline

![](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/apache%20air.jpg)


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

## Objetivo del Proyecto
El objetivo es crear un pipeline que cargue los datos automáticamente una vez al día. 
Esto permitirá mantener los datos actualizados y disponibles para análisis continuos sin intervención manual.
Además, los datos finales serán cargados en AWS S3, asegurando que estén accesibles y almacenados de manera segura.

***Proceso de creación del pipeline***

- Verificación del [código](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/first_code_python) y acceso a la API: 
  Antes de crear el DAG, verifiqué el funcionamiento del código y la correcta conexión a la API
  para asegurarme de que los datos se obtuvieran correctamente.

RESULTADO OBTENIDO:

![](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/first_code.PNG)



- Creación del [DAG:](https://github.com/elena210910/Airflow-Job_Pipeline/blob/main/DAG_python) Basado en el código verificado, creé un DAG en Airflow para automatizar el proceso de carga de datos.
  Guardado de datos en AWS S3: Una vez que los datos fueron guardados en AWS S3, verifiqué su disponibilidad y la integridad.

  

Acceso a los datos en S3: Después de guardar los datos en S3, utilicé Dask para analizarlos y extraerlos desde S3.


