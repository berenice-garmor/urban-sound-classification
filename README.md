##Urban Sound Classification Engine (Deep Learning)

Este repositorio contiene un sistema de inteligencia artificial capaz de clasificar sonidos ambientales urbanos en tiempo real mediante el uso de redes neuronales profundas. El modelo fue entrenado con el dataset **UrbanSound8K** y optimizado para ejecutarse localmente utilizando el micrófono de la computadora.

---

## Características Clave

* **Pipeline de Audio Avanzado:** Procesamiento digital de señales mediante la librería `Librosa`, aplicando normalización de amplitud, recorte automático de silencios (`Trim`) y extracción de **40 Coeficientes Cepstrales en las Frecuencias de Mel (MFCC)**.
* **Arquitectura Optimizada:** Red Neuronal Perceptrón Multicapa (MLP) robusta de 4 capas densas con técnicas de regularización (*Dropout*) para mitigar el sobreajuste.
* **Inferencia en Vivo:** Script interactivo (`grabar_y_predecir`) que captura audio ambiental por 3 segundos a través del hardware del micrófono y despliega un diagnóstico instantáneo con el nivel de confianza.
* **Monitoreo de Métricas:** Sistema validado con Matrices de Confusión y reporte de métricas clásicas (Exactitud del ~92%, Precisión y F1-Score).

---

## Arquitectura del Modelo (Main Graph)

El flujo de procesamiento de la información se estructura de forma estrictamente secuencial:

1. **Entrada (Input Layer):** Vector plano de 1x40 que condensa las características tímbricas y armónicas del audio.
2. **Capas Ocultas (Hidden Layers):** Bloques completamente conectados de 256, 512 y 256 neuronas utilizando funciones de activación **ReLU** y capas de **Dropout (0.3)** para estabilizar el aprendizaje.
3. **Capa de Salida (Output Layer):** Bloque de 10 neuronas acoplado a una función **Softmax** que calcula la distribución de probabilidad para clasificar el sonido.

---

## Tecnologías Utilizadas

* **Python 3.x**
* **TensorFlow / Keras** (Diseño y entrenamiento del modelo Deep Learning)
* **Librosa** (Procesamiento digital de señales acústicas)
* **Matplotlib & Seaborn** (Visualización de espectrogramas y matrices de confusión)
* **SoundDevice** (Captura e inferencia de audio en tiempo real)

---

## Clases que Identifica el Modelo

El sistema está entrenado para clasificar de forma precisa las siguientes 10 categorías urbanas:
1. Aire acondicionado (*Air Conditioner*)
2. Claxon de automóvil (*Car Horn*)
3. Niños jugando (*Children Playing*)
4. Ladrido de perro (*Dog Bark*)
5. Perforación/Taladro (*Drilling*)
6. Motor en ralentí (*Engine Idling*)
7. Disparo de arma (*Gun Shot*)
8. Rotomartillo (*Jackhammer*)
9. Sirena de emergencia (*Siren*)
10. Música callejera (*Street Music*)

---

## Cómo Ejecutar este Proyecto

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/TU_USUARIO/TU_REPOSITORIO.git](https://github.com/TU_USUARIO/TU_REPOSITORIO.git)
   cd TU_REPOSITORIO
