# Sistema de Detección de Rostros con Reconocimiento de "Liveness"

## Descripción
Este proyecto se centra en el desarrollo de un sistema de detección de rostros con capacidades de reconocimiento de "liveness", para mejorar la precisión en la identificación facial. Se creó un dataset personalizado y se utilizaron tanto modelos propios como preentrenados para lograr los objetivos de detección y prevención de spoofing facial.

## Objetivo

### Objetivo General
Desarrollar un sistema de detección de rostros con reconocimiento de "liveness" que optimice la precisión y confiabilidad en la identificación facial.

### Objetivos Específicos
1. Crear un dataset personalizado de imágenes faciales para entrenamiento y validación.
2. Implementar un modelo que localice rostros en imágenes/videos y realice detecciones con bounding-box y etiquetas.
3. Incorporar una verificación de "liveness" para prevenir ataques de spoofing facial.
4. Comparar el rendimiento de modelos propios con modelos preentrenados.

## Proceso

1. **Creación del Dataset**: Se creo un dataset con 1031 imágenes (517 "live" y 514 "spoof") utilizando imágenes generadas y reales, etiquetadas con MakeSense.AI.
2. **Análisis Exploratorio de Datos (EDA)**: Exploración de características del dataset, incluyendo la variabilidad en iluminación, ángulos y expresiones faciales.
3. **Aumento de Datos**: Se aplicaron técnicas de data augmentation para mejorar la robustez del modelo.
4. **Entrenamiento de Modelos**: 
   - **Modelos Propios**: Implementación de modelos de detección personalizados.
   - **Modelos Preentrenados**: Uso de MobileNetV2, ResNet50, y DenseNet169 con pesos de ImageNet.
5. **Técnicas Anti-Spoofing**: Implementación de un sistema de verificación en tiempo real, solicitando al usuario acciones aleatorias para verificar "liveness".

## Resultados
### Modelo Propio
- **Entrenamiento**: Accuracy: 86%, Loss: 31%
- **Validación**: Val Accuracy: 90%, Val Loss: 28%
- Observación: Early stopping p=4, pero se alcanzó el máximo de épocas (50). La tendencia sugiere sobreajuste si el entrenamiento continuaba más allá del límite actual.

| **Gráfico Accuracy y Loss**               | **Matriz de Confusión**               |
|-------------------------------------------|---------------------------------------|
| ![Grafico accuracy val y loss LIVENESS FACIAL modelo propio](https://github.com/user-attachments/assets/658c7a81-3597-4b64-b3bc-7470bffc8695) | ![matriz de confusion modelo propio](https://github.com/user-attachments/assets/910f5dc3-42ff-4d8c-a87e-a82cd1bbc44f) |

| **Predicción Tomada en Foto**             | **Resultados**                       |
|-------------------------------------------|---------------------------------------|
| ![predición tomada en foto modelo propio](https://github.com/user-attachments/assets/b39a3992-86a5-4c29-a743-0b9e76f8d0c8) | ![resultados modelo propio](https://github.com/user-attachments/assets/12f1248b-8682-4f14-bbc2-4993c7b474f1) |

### DenseNet169
- **Entrenamiento**: Accuracy: 94%, Loss: 16%
- **Validación**: Val Accuracy: 92%, Val Loss: 16%, F1-Score: 92%
- Observación: Estabilización temprana y buen rendimiento en validación.

| **Gráfico Accuracy y Loss**               | **Matriz de Confusión**               |
|-------------------------------------------|---------------------------------------|
| ![Grafico accuracy val y loss LIVENESS FACIAL densenet169](https://github.com/user-attachments/assets/024268d9-02ad-40fd-bac5-cfd9864772ba) | ![matriz de confusion densenet169](https://github.com/user-attachments/assets/71caa34b-b783-4e4e-adfe-186f4ae83f9f) |

| **Predicción Tomada en Foto**             | **Resultados**                       |
|-------------------------------------------|---------------------------------------|
| ![predición tomada en foto densenet169](https://github.com/user-attachments/assets/c43b018e-7976-44c8-b77d-56a79e02eb58) | ![resultados densenet169](https://github.com/user-attachments/assets/e160c6bf-e5e2-44bb-bb5b-e2c5fb698948) |


### MobileNetV2
- **Entrenamiento**: Accuracy: 94%, Loss: 16%
- **Validación**: Val Accuracy: 92%, Val Loss: 18%, F1-Score: 92%
- El modelo se estabilizó en la época 17 con buenos resultados.

| **Gráfico Accuracy y Loss**               | **Matriz de Confusión**               |
|-------------------------------------------|---------------------------------------|
| ![Grafico accuracy val y loss LIVENESS FACIAL mobilenet](https://github.com/user-attachments/assets/45bab8bf-6190-419e-8797-71b374f600b5) | ![matriz de confusion](https://github.com/user-attachments/assets/4897045e-25b0-49d2-8423-7bc85e5a197d) |

| **Predicción Tomada en Foto**             | **Resultados**                       |
|-------------------------------------------|---------------------------------------|
| ![predición tomada en foto](https://github.com/user-attachments/assets/cfa539ce-5981-4977-a770-6e0245f47798) | ![resultados](https://github.com/user-attachments/assets/1a65ebe3-5bef-4e37-b2cd-a74cb4a31096) |



## Tecnologías
- **Python**
- **Librerías**: TensorFlow, Keras, OpenCV, Pandas, NumPy, Scikit-learn

## Dataset Disponible
https://drive.google.com/drive/folders/1Gdz_dWx3wJrKaPZ6ncJsu74djELydsch?usp=sharing

## Duración del proyecto
El proyecto fue completado en el transcurso de 3 semanas. La dedicación de horas-hombre varió según mi disponibilidad a lo largo de este período.
