# Clasificación de imágenes satelitales con redes neuronales convolucionales

Implementación de un sistema de clasificación de cobertura terrestre mediante TensorFlow y Keras. Se comparan dos redes neuronales convolucionales entrenadas con imágenes del conjunto EuroSAT RGB.

## Datos

EuroSAT RGB contiene 27,000 imágenes satelitales de 64 × 64 píxeles distribuidas en diez clases. Los archivos se obtienen mediante `datasets` desde [Hugging Face](https://huggingface.co/datasets/giswqs/EuroSAT_RGB); no es necesario incluir una copia del conjunto de datos en el repositorio.

## Metodología

El conjunto de datos se dividió de forma estratificada en entrenamiento (70%), validación (15%) y prueba (15%). La primera CNN utiliza bloques de convolución y agrupamiento; la segunda incluye aumento de datos, normalización por lotes, Dropout y agrupamiento promedio global. La selección del modelo se realiza con las métricas de validación y la evaluación final se reporta sobre el conjunto de prueba.

## Archivos

- `EuroSAT_Clasificacion_CNN.ipynb`: exploración de datos, modelos, evaluación, comparación y predicciones.
- `modelo_final.keras`: arquitectura y pesos del modelo seleccionado, generado por el notebook.
- `metricas_finales.json`: métricas finales y datos del experimento, generado por el notebook.
- `requirements.txt`: dependencias del proyecto.

## Ejecución

El notebook puede ejecutarse en Google Colab con Python y TensorFlow. La primera celda instala `datasets` e `importlib-resources` cuando es necesario. Después de ejecutar todas las celdas, se generan los archivos `modelo_final.keras` y `metricas_finales.json` en el directorio de trabajo. La función `clasificar_imagen(ruta)` permite evaluar una imagen RGB a partir de su ruta.

## Referencia

Helber, P., Bischke, B., Dengel, A. y Borth, D. (2019). *EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification*. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, 12(7), 2217–2226. https://doi.org/10.1109/JSTARS.2019.2918242
