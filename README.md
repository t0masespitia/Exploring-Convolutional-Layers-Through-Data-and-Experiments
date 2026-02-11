# Exploring-Convolutional-Layers-Through-Data-and-Experiments

# Convolutional Neural Networks on Fashion-MNIST

Este proyecto explora el uso de **redes neuronales convolucionales (CNN)** como componentes arquitectónicos explícitos, en lugar de tratarlas como cajas negras. A través del dataset **Fashion-MNIST**, se analizan las decisiones de diseño en capas convolucionales y su impacto en el desempeño, comparándolas con un modelo base totalmente conectado. El objetivo principal es comprender el **sesgo inductivo** introducido por la convolución y cómo este se alinea con la estructura de los datos de tipo imagen.

---

## Getting Started

Estas instrucciones permiten obtener una copia del proyecto y ejecutarlo localmente para fines de desarrollo, experimentación y evaluación. El proyecto está implementado en **Python con PyTorch** y se distribuye como un notebook ejecutable.

---

## Prerequisites

Para ejecutar este proyecto se requiere:

- Python 3.9 o superior  
- Entorno virtual (recomendado)
- PyTorch
- torchvision
- pandas
- matplotlib

### Ejemplo de instalación de dependencias
pip install torch torchvision pandas matplotlib

---

## Installing
primero clonar el repositorio : 
git clone <url-del-repositorio>
cd <nombre-del-repositorio>

Segundo instalar dependencias : 
pip install -r requirements.txt

---

## Dataset Description

Se utiliza el dataset Fashion-MNIST, compuesto por 60.000 imágenes de entrenamiento y 10.000 imágenes de prueba, distribuidas en 10 clases de prendas de vestir.
Cada imagen tiene resolución 28×28 píxeles, un solo canal (escala de grises) y representa una categoría de ropa o calzado.

El dataset es adecuado para CNN porque las clases se distinguen por patrones espaciales locales como bordes, contornos y texturas. Los datos se cargan utilizando torchvision.datasets.FashionMNIST, garantizando reproducibilidad.

---

## Architecture Design

Baseline Model (Non-Convolutional)

Flatten

Dense (256) + ReLU

Dense (10)

---

## Convolutional Neural Network

Input (1×28×28)
→ Conv(3×3, 32) + ReLU + MaxPool(2×2)
→ Conv(3×3, 64) + ReLU + MaxPool(2×2)
→ Flatten
→ Dense(128) + ReLU
→ Dense(10)

---

## Experimental Results

Se realizó un experimento controlado modificando únicamente el tamaño del kernel convolucional (3×3 vs 5×5), manteniendo fijos todos los demás hiperparámetros.

Resultados observados:

El kernel 3×3 mostró mejor desempeño en términos de accuracy.

El kernel 5×5 incrementó el costo computacional y tendió a perder detalle local en imágenes pequeñas.

Ambos modelos superaron al baseline completamente conectado.

Este experimento evidencia el impacto directo de las decisiones arquitectónicas en el aprendizaje.

---

## Interpretation

Las capas convolucionales superan al modelo baseline porque explotan explícitamente la estructura espacial de las imágenes mediante conectividad local y compartición de pesos. Esto permite aprender patrones visuales relevantes de forma más eficiente y generalizar mejor.

El sesgo inductivo introducido por la convolución asume localidad, estacionariedad y composicionalidad jerárquica, lo cual es coherente con datos visuales. Sin embargo, este tipo de arquitectura no es adecuada para datos tabulares o problemas donde no existe una noción de vecindad espacial significativa.

--- 

## Built With

- Python

- PyTorch – Framework de deep learning

- torchvision – Manejo de datasets e imágenes

- pandas – Análisis de datos

- matplotlib – Visualización

---

## Authors

Tomás Espitia Quiroga
Estudiante de Ingeniería de Sistemas
Escuela Colombiana de Ingeniería Julio Garavito

