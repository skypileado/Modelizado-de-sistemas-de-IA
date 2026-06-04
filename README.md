# Modelizado-de-sistemas-de-IA

Materia: Modelizado de Sistemas de IA 🤖
Este repositorio alberga los trabajos prácticos (TPs) desarrollados a lo largo de la cursada de Modelizado de Sistemas de IA. El propósito central es documentar el progreso académico, la experimentación y la implementación práctica de diversos enfoques y modelos de inteligencia artificial.

📁 Trabajos Prácticos Entregados
TP 1: Sistema Experto – Empresa Constructora
Archivo: P1_Sistemas_Expertos.ipynb

Descripción: Diseño y desarrollo de un sistema basado en reglas para automatizar la evaluación de riesgos operativos y la asignación óptima de maquinaria en proyectos de construcción.

Estado: ✅ Completado

TP 2: Optimización de Cronogramas mediante Algoritmos Genéticos
Archivo: P2_Algoritmos_Genéticos.ipynb

Descripción: Aplicación de computación evolutiva para resolver un problema de optimización de tiempos y recursos (Makespan) en una obra civil.

El Desafío: Planificar la secuencia de 10 tareas críticas bajo la restricción estricta de no superar un máximo de 10 operarios en simultáneo.

Resultados Clave:

El algoritmo convergió exitosamente en un cronograma óptimo de 18 días.

Se diseñó una Función de Aptitud (Fitness Function) con penalización severa para descartar soluciones que violaran el límite de personal.

Se implementaron mecanismos de Selección por Torneo y Elitismo para preservar las mejores soluciones a lo largo de las generaciones.

Estado: ✅ Completado

TP 3: Clasificación de Riesgo Crediticio con Perceptrón
Archivo: P3_Preceptron_simple.ipynb

Descripción: Implementación de un Perceptrón Simple para la evaluación y aprobación automatizada de créditos financieros.

El Desafío: Hallar la frontera de decisión óptima para clasificar clientes en "Bajo Riesgo" y "Alto Riesgo" dentro de un espacio bidimensional (Puntaje Crediticio vs. Ratio de Ahorro).

Resultados Clave:

El modelo logró un 100% de precisión (Accuracy), confirmando la separabilidad lineal del conjunto de datos.

Se incorporó una Función de Activación Sigmoide para mapear la salida como una probabilidad continua (entre 0 y 1).

Se evaluó el impacto de las regularizaciones L1 (Lasso) y L2 (Ridge), validando cómo L1 introduce dispersión (sparsity) al anular los pesos de las variables irrelevantes.

Estado: ✅ Completado

TP 4: Clasificación de Indumentaria con Redes Neuronales Multicapa (MLP)
Archivo: P4_RRNN_multicapa.ipynb

Descripción: Diseño y entrenamiento de una red neuronal artificial profunda (MLP) para la clasificación de imágenes del dataset Fashion MNIST (28x28 píxeles).

Arquitectura de la Red:

Capa de Entrada: Flatten (784 características).

Capas Ocultas: Dos capas densas (de 128 y 64 neuronas) con funciones de activación ReLU para la extracción de patrones complejos.

Capa de Salida: 10 neuronas con activación Softmax para obtener la distribución de probabilidad multiclase.

Resultados Clave:

Precisión alcanzada en el conjunto de test: 87.76%.

Para mitigar el sobreajuste (overfitting), se utilizó Early Stopping (paciencia = 5); el entrenamiento se interrumpió en la época 17 y se restauraron los mejores pesos obtenidos en la época 12.

Estado: ✅ Completado

TP 5: Predicción de Tendencias
Archivo: P5_PLANTILLA_prediccion.ipynb

Descripción: Construcción y entrenamiento de un modelo lineal simple configurado como baseline (punto de referencia) para futuras iteraciones predictivas.

Estado: ✅ Completado
