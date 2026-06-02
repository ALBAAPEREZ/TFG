# Detección de imágenes y videos falsos (Deepfake Detection) 🕵️‍♀️💻

Este repositorio contiene el código fuente en formato de cuadernos de Jupyter, los conjuntos de datos y la configuración experimental correspondientes al **Trabajo de Fin de Grado en Ingeniería Informática** titulado *"Detección de imágenes y videos falsos"*, realizado en la **Universidad de La Laguna (ULL)**.

El objetivo principal de este proyecto es evaluar y realizar un estudio comparativo de rendimiento de cuatro arquitecturas de aprendizaje profundo para la clasificación de rostros reales frente a manipulaciones sintéticas (*deepfakes*).

---

## 🚀 Resumen del Proyecto

Ante el auge de la desinformación y el perfeccionamiento de los contenidos sintéticos, este trabajo analiza la robustez, capacidad de generalización y eficiencia computacional de diferentes paradigmas de Visión por Computador. El estudio se evalúa utilizando el dataset de referencia **FaceForensics++**, analizando críticamente el impacto que tienen los distintos niveles de compresión de vídeo (**C0** sin compresión, **C23** compresión intermedia y **C40** alta compresión) en la tasa de acierto de los de modelos.

### 🧠 Arquitecturas Evaluadas
* **XceptionNet:** Red convolucional (CNN) basada en convoluciones separables en profundidad (*baseline* clásico).
* **EfficientNet-B3:** CNN moderna optimizada mediante un escalado compuesto balanceado.
* **MesoInception-4:** Arquitectura compacta diseñada para detectar anomalías a nivel mesoscópico.
* **Vision Transformer (ViT-Base/16):** Modelo basado en mecanismos de atención global.

---

## 📁 Estructura del Repositorio

El proyecto está organizado de manera secuencial a través de los siguientes archivos y directorios:

```text
├── data/
│   └── registro_datos.csv                     # CSV con los metadatos y registros del dataset base C23
│
├── notebooks/                                    # Cuadernos de Jupyter con todo el desarrollo del TFG
│   ├── 00_Comienzo_Procesamiento_de_fotos.ipynb  # Explicación y decisiones clave del diseño del pipeline
│   ├── 00_Preparación dataset.ipynb              # Análisis exploratorio, validación e integridad del dataset base C23
│   ├── 01_Train_XceptionNet.ipynb                # Diseño, entrenamiento y Early Stopping de la red XceptionNet
│   ├── 02_Train_EfficientNet.ipynb               # Ajuste y entrenamiento de la arquitectura EfficientNet-B3
│   ├── 03_Train_MesoInception.ipynb              # Entrenamiento optimizado de MesoInception-4 (red ligera)
│   ├── 04_Train_VisionTransformers.ipynb         # Ajuste fino y Label Smoothing para Vision Transformers (ViT)
│   ├── 05_LOSS_Evaluacion_y_Comparativa_Final.ipynb # Evaluación exhaustiva en C23 y análisis de calibración (Log Loss)
│   ├── 06_Processamiento_dataset_C40.ipynb       # Extracción facial con MTCNN para el conjunto de alta compresión (C40)
│   ├── 07_Testeo_Modelos_C40.ipynb               # Evaluación de robustez de los 4 modelos frente a datos C40
│   ├── 08_Procesamiento_dataset_C0.ipynb         # Extracción facial con MTCNN para el conjunto sin compresión (C0 / RAW)
│   ├── 09_Testeo_Modelos_C0.ipynb                # Evaluación de rendimiento de los modelos frente a vídeos de alta calidad C0
│   ├── 10_Comparativa_compresion_dataset.ipynb   # Análisis cruzado final y estudio del impacto de las 3 compresiones
│
├── resultados                                    # Contiene imágenes de los notebooks en formato png
├── resultados_finales                            # Contiene tablas resultados de comapraciones en formato csv
└── README.md                                     # Este archivo informativo
