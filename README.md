# Tomato Leaf Disease Detection with YOLO

Proyecto de visión por computador para detectar y clasificar enfermedades en hojas de tomate usando aprendizaje profundo y el modelo YOLOv8.

## Descripción

El objetivo del proyecto es entrenar un modelo capaz de identificar visualmente hojas de tomate y clasificarlas según su estado sanitario. El modelo detecta la región de interés mediante una caja delimitadora y predice la clase correspondiente, indicando además un porcentaje de confianza.

El proyecto fue desarrollado como trabajo final para la asignatura de Visión por Computador e Inteligencia Artificial.

## Dataset

Se utilizó el dataset público **Tomato Leaf Disease**, disponible en Kaggle. El conjunto de datos contiene imágenes de hojas de tomate anotadas en formato YOLO.

Clases utilizadas:

- Tomato__BacterialSpot
- Tomato__EarlyBlight
- Tomato__Healthy
- Tomato__LateBlight
- Tomato__LeafMold
- Tomato__MosaicVirus
- Tomato__SeptoriaLeafSpot
- Tomato__SpiderMites
- Tomato__TargetSpot
- Tomato__YellowLeafCurlVirus

Debido a limitaciones de tiempo y cómputo en Google Colab, se trabajó con un subconjunto balanceado:

| Conjunto | Imágenes por clase | Total |
|---|---:|---:|
| Entrenamiento | 220 | 2.200 |
| Validación | 75 | 750 |
| Prueba | 75 | 750 |

## Modelo utilizado

Se utilizó **YOLOv8n**, una versión liviana de YOLOv8, mediante transferencia de aprendizaje.

La elección de YOLO se debe a que permite realizar detección y clasificación en una sola etapa, prediciendo:

- Caja delimitadora
- Clase de enfermedad
- Confianza de la predicción

## Entrenamiento

Configuración principal:

| Parámetro | Valor |
|---|---:|
| Modelo | YOLOv8n |
| Épocas | 20 |
| Tamaño de imagen | 640 x 640 |
| Batch size | 16 |
| Entorno | Google Colab |
| GPU | Tesla T4 |

## Resultados

Resultados finales sobre el conjunto de prueba:

| Métrica | Valor |
|---|---:|
| Precision media | 0.9867 |
| Recall medio | 0.9681 |
| mAP50 | 0.9911 |
| mAP50-95 | 0.9807 |

Estos resultados indican un buen desempeño del modelo tanto en la localización de la hoja o región anotada como en la clasificación de la enfermedad.

## Resultados visuales

El modelo genera imágenes con:

- Caja delimitadora sobre la hoja o región detectada
- Clase predicha
- Porcentaje de confianza

También se analizó la matriz de confusión para identificar aciertos y posibles errores entre clases similares.

## Limitaciones

El modelo fue evaluado dentro de las condiciones del dataset utilizado. Para una aplicación real en campo, sería necesario probarlo con imágenes tomadas en diferentes condiciones de iluminación, fondo, distancia, orientación y calidad de cámara.

## Archivos principales

- `LeafDisease_DeepLearning.ipynb`: notebook principal con la preparación del dataset, entrenamiento, validación y análisis de resultados.
- `README.md`: descripción general del proyecto.

## Conclusión

El proyecto demuestra que un modelo YOLOv8n puede detectar y clasificar enfermedades en hojas de tomate con alto desempeño usando un subconjunto balanceado del dataset. La solución puede servir como base para futuras aplicaciones de apoyo al diagnóstico visual en cultivos.
