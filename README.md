# EXAMEN FINAL - ESTADISTICA COMPUTACIONAL

## Ejercicio 1: Limpieza de datos - Boston Housing

Este proyecto incluye un script de Bash llamado `limpieza_datos.sh` que automatiza el proceso de descarga, limpieza y estructuración del dataset de Boston Housing. 

### Descripción

El script realiza las siguientes tareas:
1. Descarga el dataset desde una URL pública.
2. Extrae el catalogo
3. Extrae los datos
4. Genera un archivo limpio y estructurado en formato CSV.

### Herramientas necesarias
Asegúrate de tener las siguientes herramientas instaladas:
- `wget`: Para descargar archivos desde la web.
- `sed` y `awk`: Para limpieza y manipulación de datos.

En caso de no tenerlas se puede hacer lo siguiente:

Instalación del comando `wget` en macOS

Utiliza Homebrew para instalar wget
```bash
brew install wget
```

Una vez instalado, verifica que wget o el comando instalado funciona con:
```bash
wget --version
```

### Pasos para ejecutar el script

#### 1. Clonar o descargar el archivo
Descarga el archivo `limpieza_datos.sh` y colócalo en el directorio de trabajo deseado.

Abre una terminal y navega a ese directorio:
```bash
cd /ruta/del/directorio
```

#### 2. Hacer el script ejecutable
Antes de ejecutar el script, dale permisos de ejecución con el siguiente comando:
```bash
chmod +x limpieza_datos.sh
```

#### 3. Ejecutar el script
Ejecuta el script con el siguiente comando:
```bash
./limpieza_datos.sh
```

#### 4. Archivos resultantes de la ejecución
El script generará 3 archivos  boston_housing_raw.txt, catalogo.txt, boston_housing_clean.csv

#### 5. Verificar el resultado
Puedes verificar las primeras líneas del archivo boston_housing_clean.csv con:
```bash
head boston_housing_clean.csv
```

## Ejercicio 2: Análisis univariado de variables en R

### Descripción

Este script realiza un análisis univariado para calcular estadísticas descriptivas de todas las variables del dataset, incluyendo:

- Mínimo
- Máximo
- Media
- Mediana
- Desviación estándar
- Primer cuartil (Q1)
- Tercer cuartil (Q3)

Los resultados están organizados de tal manera que cada fila corresponde a una variable, y los valores están redondeados a 4 decimales.

### Requisitos Previos

1. Tener instalado R en tu sistema.
2. Contar con los paquetes `dplyr` y `tidyr` instalados. El script se encargará de instalarlos automáticamente si no están disponibles.

### Archivos Requeridos

1. Dataset de entrada: `boston_housing_clean.csv`
Debe contener las variables a analizar, con las columnas separadas por comas y la primera fila como nombres de las columnas.

2. Script de R: `analisis_univariado.R`
Este archivo realiza el análisis univariado y genera el archivo de salida.

### Instrucciones de Uso

Paso 1: Preparar el entorno

Coloca el archivo `boston_housing_clean.csv` y el script `analisis_univariado.R` en el mismo directorio.

Paso 2: Ejecutar el script

Abre una terminal y navega al directorio donde se encuentran los archivos:
```bash
cd /ruta/a/tu/directorio
```

Ejecuta el script con el siguiente comando:
```bash
Rscript analisis_univariado.R
```

Paso 3: Revisar los resultados

El script generará un archivo llamado `analisis_univariado.csv` en el mismo directorio.

Este archivo contiene las estadísticas descriptivas de cada variable, con las columnas siguientes:

Variable: Nombre de la variable.

Minimo, Maximo, Media, Mediana, Desviacion, Q1, Q3: Estadísticas descriptivas redondeadas a 4 decimales.

El archivo de salida tiene la siguiente estructura:

| Variable | Minimo  | Maximo  | Media  | Mediana | Desviacion | Q1    | Q3    |
|----------|---------|---------|--------|---------|------------|-------|-------|
| CRIM     | 0.0063  | 88.9760 | 3.6135 | 0.2565  | 8.6021     | 0.0820 | 3.6770 |
| ZN       | 0.0000  | 100.0000| 11.3630| 0.0000  | 23.3220    | 0.0000| 12.5000|
| INDUS    | 0.4600  | 27.7400 | 11.1400| 9.6900  | 6.8600     | 5.1900| 18.1000|


## Ejercicio 3: Análisis Bivariado de Boston Housing

### Descripción

Este script realiza un análisis bivariado entre cada variable independiente y la variable objetivo (MEDV) utilizando el dataset de Boston Housing. Los resultados incluyen:

- Matriz de correlación entre todas las variables.
- Gráficos bivariados (diagramas de dispersión) entre MEDV y cada variable independiente.
- Los resultados se exportan automáticamente a un archivo PDF llamado analisis_bivariado_MEDV.pdf.

### Requisitos del Entorno

Asegúrate de tener R instalado en tu sistema. Además, las siguientes librerías son necesarias:

- ggplot2 para la visualización.
- corrplot para la matriz de correlación.
- gridExtra para organizar gráficos.

Si no tienes estas librerías, el script se encargará de instalarlas automáticamente.

### Archivos Necesarios

- `Analisis_Bivariado.R`: Script principal para el análisis bivariado.
- `boston_housing_clean.csv`: Dataset limpio en formato CSV.

### Pasos para la Ejecución

1. Preparar el Archivo
Guarda el script proporcionado como `Analisis_Bivariado.R` en tu directorio de trabajo.

2. Ubicar el Dataset
Asegúrate de que el archivo `boston_housing_clean.csv` (dataset limpio) esté en el mismo directorio donde se encuentra el script `Analisis_Bivariado.R`.

3. Ejecutar el Script
Ejecuta el script en R utilizando la terminal o la línea de comandos:

```bash
Rscript Analisis_Bivariado.R
```

4. Salida del Script

- Matriz de Correlación: Se imprime la correlación entre todas las variables.
- Gráficos Bivariados: Diagramas de dispersión con líneas de regresión lineal entre MEDV y cada variable independiente.

Todos los resultados se guardan en el archivo analisis_bivariado_MEDV.pdf, ubicado en el mismo directorio.


## Ejercicio 4: Visualizaciones Relevantes en R

### Descripción

Este script realiza visualizaciones relevantes del dataset Boston Housing para explorar las relaciones entre variables y entender su comportamiento estadístico. Las visualizaciones generadas son:

- Scatter plots: Para analizar la relación entre variables predictoras y la variable objetivo (MEDV).
- Q-Q Plots: Para evaluar la normalidad de las variables importantes.
- Box Plots: Para identificar outliers.
- Histogramas: Para observar la distribución de las variables clave.
  
Todas las visualizaciones se exportan a un archivo PDF llamado visualizaciones_relevantes.pdf.

### Requisitos del Entorno

Asegúrate de tener R instalado en tu sistema. Además, las siguientes librerías son necesarias:

- ggplot2 para la visualización.
- gridExtra para organizar gráficos.

Si no tienes estas librerías, el script se encargará de instalarlas automáticamente.

### Archivos Necesarios

- `visualizaciones_relevantes.R`: Script principal para el análisis bivariado.
- `boston_housing_clean.csv`: Dataset limpio en formato CSV.

### Pasos para la Ejecución

1. Preparar el Archivo
Guarda el script proporcionado como `visualizaciones_relevantes.R` en tu directorio de trabajo.

2. Ubicar el Dataset
Asegúrate de que el archivo `boston_housing_clean.csv` (dataset limpio) esté en el mismo directorio donde se encuentra el script `visualizaciones_relevantes.R`.

3. Ejecutar el Script
Ejecuta el script en R utilizando la terminal o la línea de comandos:

```bash
Rscript visualizaciones_relevantes.R
```

4. Salida del Script

El script generará un archivo PDF llamado visualizaciones_relevantes.pdf, que contiene las visualizaciones listadas en descripción.


## Ejercicio 5: Guardado en formato Feather

### Descripción

El dataset procesado se guarda en formato Feather, que es un formato eficiente y rápido para el manejo de datos.

### Requisitos del Entorno

Asegúrate de tener R instalado en tu sistema. Además, las siguientes librerías son necesarias:

- dplyr: Para realizar transformaciones y filtrado.
- arrow: Para guardar el dataset en formato Feather.

Si no tienes estas librerías, el script se encargará de instalarlas automáticamente.

### Archivos Necesarios

- `procesado_variables.R`: Script principal para transformar variables y guardar resultado en formato feather.
- `boston_housing_clean.csv`: Dataset limpio en formato CSV.

### Pasos para la Ejecución

1. Preparar el Archivo
Guarda el script proporcionado como `procesado_variables.R` en tu directorio de trabajo.

2. Ubicar el Dataset
Asegúrate de que el archivo `boston_housing_clean.csv` (dataset limpio) esté en el mismo directorio donde se encuentra el script `procesado_variables.R`.

3. Ejecutar el Script
Ejecuta el script en R utilizando la terminal o la línea de comandos:

```bash
Rscript procesado_variables.R
```

4. Salida del Script

El script generará un archivo llamado `boston_processed.feather`, que contiene:

### Validación del Resultado
Para verificar el archivo Feather generado, puedes cargarlo en R de la siguiente manera:

```R
library(arrow)
data <- read_feather("boston_processed.feather")
head(data)
```

## Ejercicio 6, 7 y 8: Entrenamiento, evaluación y guardado de un modelo random forest en python

### Descripción General

Este script realiza las siguientes tareas:

- Carga del dataset en formato Feather.
- Entrenamiento de un modelo Random Forest Regressor para predecir la variable objetivo MEDV.
- Evaluación del modelo utilizando las métricas Error Cuadrático Medio (MSE) y Coeficiente de Determinación (R²).
- Guardado del modelo entrenado en un archivo model.pkl.

Este procedimiento se utiliza para crear un modelo predictivo eficiente y preparado para futuras implementaciones.

### Requisitos del Entorno

Las siguientes librerías son requeridas para ejecutar el script:

- pandas: Manipulación de datos.
- numpy: Operaciones numéricas.
- scikit-learn: Entrenamiento y evaluación del modelo.
- pyarrow: Cargar datasets en formato Feather.
- joblib: Guardado del modelo entrenado.

Instala todas las librerías (en caso de no tenerlas) utilizando el siguiente comando:

```bash
pip install pandas numpy scikit-learn pyarrow joblib
```

### Archivos Necesarios

- boston_processed.feather: Dataset procesado con las transformaciones relevantes.
- random_forest.py: Script principal para el entrenamiento, evaluación y guardado del modelo.

### Pasos para la Ejecución

1. Preparar los Archivos
Coloca el archivo `boston_processed.feather` y el script `random_forest.py` en el mismo directorio de trabajo.

2. Ejecutar el Script
Ejecuta el script desde la terminal con el siguiente comando:

```bash
python random_forest.py
```

3. Funcionamiento del Script

Cargar el Dataset: El archivo `boston_processed.feather` se carga utilizando la librería pyarrow.
Dividir el Dataset: El dataset se divide en 80% para entrenamiento y 20% para prueba usando train_test_split.
Entrenar el Modelo: Se utiliza el modelo RandomForestRegressor.
Evaluar el Modelo: Se calculan MSE y R² en el conjunto de prueba.
Guardar el Modelo: El modelo entrenado se guarda en un archivo model.pkl utilizando la librería joblib.

4. Salida del Script
En la consola se mostrarán los resultados de evaluación, por ejemplo:

```plaintext
Cargando el dataset procesado en formato Feather...
Dividiendo el dataset en conjunto de entrenamiento y prueba...
Entrenando el modelo Random Forest Regressor...
Evaluando el modelo en el conjunto de prueba...
Error Cuadrático Medio (MSE): 9.06
Coeficiente de Determinación (R²): 0.88
Guardando el modelo entrenado en 'model.pkl'...
Proceso completado. El modelo ha sido guardado.
```

5. Validación del Modelo

Para cargar y validar el modelo guardado, utiliza el siguiente código en Python:
```python
import joblib

# Cargar el modelo entrenado
model = joblib.load("model.pkl")

# Hacer predicciones con nuevos datos
nuevos_datos = [[0.1, 25, 5.3, 0, 0.5, 6.2, 45, 5.0, 2, 300, 15, 390, 12]]
prediccion = model.predict(nuevos_datos)
print("Predicción para nuevos datos:", prediccion)
```

## Ejercicio 9 y 10: Creación de API REST con FastAPI para Predicción y Estadísticas

### Descripción General

Este proyecto implementa una API REST utilizando FastAPI con los siguientes endpoints:

1. POST /predict: Recibe un JSON con las variables independientes.

Devuelve la predicción de la variable objetivo MEDV utilizando un modelo Random Forest previamente entrenado.

2. GET /stats: Devuelve estadísticas básicas de las predicciones realizadas.

- Número total de solicitudes.
- Promedio de las predicciones.
- Valor máximo y mínimo de las predicciones.

### Requisitos del Proyecto

Librerías Requeridas

- fastapi: Framework para crear APIs en Python.
- uvicorn: Servidor ASGI para correr la API.
- pydantic: Validación de datos de entrada.
- joblib: Para cargar el modelo entrenado.
- pandas: Manejo de datos en memoria para almacenar predicciones.

```bash
pip install fastapi uvicorn pydantic joblib pandas
```

### Archivos Necesarios

- model.pkl: Modelo Random Forest entrenado para predecir MEDV.
- app.py: Archivo principal que implementa la API REST.

### Estructura del Proyecto
La estructura de archivos del proyecto debe ser la siguiente:

```plaintext
project/
│-- model.pkl           # Modelo entrenado
│-- app.py              # Script principal de la API
│-- requirements.txt    # Librerías necesarias
```

### Implementación del Script app.py

Aquí se describen los dos endpoints principales implementados:

1. Endpoint /predict
Este endpoint recibe un JSON con las variables independientes y devuelve la predicción de MEDV.

Salida: La predicción de MEDV:
```json
{
  "prediction": 22.5
}
```

2. Endpoint /stats
Este endpoint devuelve estadísticas de las predicciones realizadas hasta el momento.

Salida: Ejemplo de respuesta:
```json
{
  "total_requests": 3,
  "mean_prediction": 21.8,
  "max_prediction": 25.5,
  "min_prediction": 19.6
}
```

### Ejecución del Proyecto
Sigue los pasos a continuación para ejecutar la API:

1. Iniciar el Servidor FastAPI

Ejecuta el siguiente comando en la terminal:

```bash
uvicorn app:app --reload
```

2. Abrir la Documentación de la API
Una vez el servidor esté corriendo, abre tu navegador y visita:

```plaintext
http://127.0.0.1:8000/docs
```

Aquí podrás interactuar con los endpoints /predict y /stats usando la interfaz Swagger de FastAPI.

### Pruebas de los Endpoints

1. Probar el Endpoint /predict

- Selecciona el endpoint POST /predict en Swagger.
- Introduce un JSON con las variables requeridas.
- Haz clic en "Execute" para enviar la solicitud.
- Recibirás una respuesta con la predicción.

2. Probar el Endpoint /stats
- Selecciona el endpoint GET /stats en Swagger.
- Haz clic en "Execute".
- Recibirás estadísticas de las predicciones realizadas hasta el momento.

2.1 Ejemplo de Uso con curl
También puedes probar los endpoints usando curl abriendo otra terminal e ingresando lo siguiente:

Realizar una Predicción

```bash
curl -X POST "http://127.0.0.1:8000/predict" -H "Content-Type: application/json" -d '{
  "CRIM": 0.1,
  "ZN": 25.0,
  "INDUS": 5.0,
  "CHAS": 0,
  "NOX": 0.5,
  "RM": 6.2,
  "AGE": 45.0,
  "DIS": 4.0,
  "RAD": 2,
  "TAX": 300,
  "PTRATIO": 15.0,
  "B": 390.0,
  "LSTAT": 12.0
}'
```

Obtener Estadísticas

```bash
curl -X GET "http://127.0.0.1:8000/stats"
```


## Ejercicio 11: Configurar una base de datos MySQL en RDS de AWS y almacenar solicitudes y predicciones del endpoint /predict.

Lo intente pero no pude conectarlo.

![image](https://github.com/user-attachments/assets/6825098f-0a51-4695-ad52-01e27c45f9e4)


## Ejercicio 12.1: Contenerizar la aplicación (API + modelo) con Docker.

### Instrucciones para Contenerizar y Probar la API con Docker

1. Crear el Dockerfile

Descarga los archivos del proyecto app.py, model.pkl, requirements.txt y Dockerfile 

Estructura del proyecto

```plaintext
.
|-- app.py              # Archivo principal de la API
|-- model.pkl           # Archivo del modelo entrenado
|-- requirements.txt    # Archivo con dependencias de Python
|-- Dockerfile          # Archivo de configuración Docker
```

2. Verificar el Archivo requirements.txt
   
Antes de continuar, verifica que requirements.txt contiene las dependencias necesarias para ejecutar la API:

- plaintext
- Copy code
- fastapi
- uvicorn
- gunicorn
- joblib
- numpy
- pandas
- mysql-connector-python

Si el archivo no existe, créalo en el directorio principal con el contenido anterior.

3. Construir la Imagen Docker
   
Abre una terminal en el directorio principal del proyecto (donde está el Dockerfile) y ejecuta el siguiente comando:

```bash
docker build -t fastapi-docker-app .
```

Explicación del Comando:

-t fastapi-docker-app: Asigna un nombre a la imagen Docker.
.: Especifica el directorio actual como contexto de construcción.

Si la construcción es exitosa, verás un mensaje indicando que la imagen ha sido creada.

4. Ejecutar el Contenedor Docker
5. 
Una vez que la imagen está creada, ejecuta el siguiente comando para probar la aplicación localmente:

```bash
docker run -d -p 80:80 fastapi-docker-app
```

Explicación del Comando:

-d: Ejecuta el contenedor en segundo plano.
-p 80:80: Mapea el puerto 80 del contenedor al puerto 80 de tu máquina local.
fastapi-docker-app: Es el nombre de la imagen que construiste.

5. Verificar la API en el Navegador
   
Abre un navegador web.

Ingresa la siguiente URL:

Documentación de la API (Swagger UI): http://127.0.0.1:80/docs
Redirección de la API: http://127.0.0.1:80

Si todo está configurado correctamente, deberías ver la documentación interactiva de FastAPI.


## Ejercicio 12.2: Despliegue de Aplicación FastAPI con Docker en AWS EC2

Pude crear la instancia pero desafortunamente no pude cargar la imagen docker en la instancia

<img width="1708" alt="image" src="https://github.com/user-attachments/assets/606a4e84-c858-48b6-8f92-3f7a0f31779b">

<img width="938" alt="image" src="https://github.com/user-attachments/assets/0ef336a8-13d5-4340-86d0-11ee49bd5c0c">

## Ejercicio 13: Crear una Shiny App en R con hallazgos del análisis.

Boston Housing Analysis - Shiny App

### Descripción

Esta aplicación Shiny permite realizar un análisis visual e interactivo de los datos del conjunto Boston Housing. Ofrece funcionalidades para visualizar:

- Gráficos de dispersión (scatterplots).
- Estadísticas descriptivas básicas.
La aplicación está desarrollada en R utilizando la biblioteca Shiny y ggplot2.

### Ejecutar la Shiny App

Sigue estos pasos para ejecutar la aplicación desde la terminal:

Abrir la terminal y ubicarte en el directorio donde guardaste app.R y el archivo CSV.

```bash
R -e "shiny::runApp('app.R', port=5050, launch.browser=TRUE)"
```
port = 5050: Especifica un puerto diferente al usado por tu API (si está corriendo en otro puerto).
launch.browser = TRUE: Abre automáticamente la aplicación en el navegador.



