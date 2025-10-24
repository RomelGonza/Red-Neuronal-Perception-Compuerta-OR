# IMPLEMENTACIÓN DE UN PERCEPTRÓN (RED NEURONAL MONOCAPA) PARA LA COMPUERTA LÓGICA OR

## 1. Introducción

Este repositorio contiene una implementación didáctica del algoritmo del **Perceptrón**, la forma más simple de una red neuronal artificial (monocapa), utilizada para clasificar datos linealmente separables.

El objetivo de este proyecto es entrenar el Perceptrón para simular el comportamiento de la **Compuerta Lógica OR**.

## 2. Estructura del Proyecto

El código fuente principal se encuentra diseñado para ser ejecutado paso a paso en un **Google Colab Notebook**.

## 3. Algoritmo del Perceptrón

### 3.1. Clase Perceptron

La clase `Perceptron` se define con los siguientes componentes clave:

* **Inicialización (`__init__`)**: Establece la tasa de aprendizaje ($\eta$) y el número de épocas.
* **Entrenamiento (`fit`)**:
    * Inicializa los pesos ($w$) y el sesgo ($w_0$).
    * Itera sobre las épocas y los ejemplos de entrenamiento.
    * Aplica la **Regla de Actualización del Perceptrón**: $\Delta w = \eta (y - \hat{y}) x$.
    * Registra el número de errores en cada época.
* **Entrada Neta (`net_input`)**: Calcula la suma ponderada: $z = w \cdot x + b$.
* **Predicción (`predict`)**: Aplica la función de activación (escalón de Heaviside): $\hat{y} = 1$ si $z \ge 0$, y $0$ en caso contrario.

### 3.2. Compuerta OR

| Entrada $x_1$ | Entrada $x_2$ | Salida $y$ |
|:-------------:|:-------------:|:----------:|
| 0             | 0             | 0          |
| 0             | 1             | 1          |
| 1             | 0             | 1          |
| 1             | 1             | 1          |

## 4. Requisitos

El código está escrito en Python y requiere las siguientes librerías:

* `numpy`: Para operaciones numéricas y manejo de vectores y matrices.
* `matplotlib`: Para la visualización de la curva de error y la frontera de decisión.

## 5. Resultados y Visualización

El script genera dos visualizaciones clave tras el entrenamiento:

1.  **Evolución del Aprendizaje**: Un gráfico que muestra la reducción del número de errores de clasificación a lo largo de las épocas, demostrando la convergencia del algoritmo.
2.  **Frontera de Decisión**: Un gráfico bidimensional que ilustra cómo el Perceptrón ha trazado una línea (frontera de decisión) para separar las clases de la compuerta OR (clase 0 de clase 1), confirmando que esta compuerta es linealmente separable.
