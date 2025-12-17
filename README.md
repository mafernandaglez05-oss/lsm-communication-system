# Embedded LSM Communication System

## Descripción General

Este proyecto implementa un sistema embebido diseñado para facilitar la comunicación entre personas sordomudas y oyentes mediante el uso de visión por computadora, sensores flexibles y aprendizaje automático. 

El sistema es capaz de:
- Traducir **Lengua de Señas Mexicana (LSM)** a texto y audio en tiempo real.
- Convertir **voz hablada** en texto mostrado para la persona sordomuda.

Actualmente, el sistema reconoce el **abecedario en LSM** y opera mediante una arquitectura modular compuesta por tres elementos principales:

- **Raspberry Pi 5 (módulo maestro):**  
  Encargada del procesamiento de visión por computadora, inferencia con redes neuronales, reproducción de audio y visualización en una pantalla táctil.

- **Raspberry Pi 3:**  
  Responsable del reconocimiento de voz, comunicación con el guante inteligente y despliegue de información en una pantalla táctil y una pantalla LCD (16x2).

- **Guante inteligente con ESP32:**  
  Equipado con sensores de flexión y una IMU (acelerómetro + giroscopio) para detectar movimientos de la mano y enviar las señas reconocidas al sistema principal.

---

## Características del Sistema

- Traducción de señas en LSM a texto
- Síntesis de voz para reproducir en altavoz lo interpretado por visión
- Reconocimiento de voz con transcripción visual para usuarios sordomudos
- Interfaz gráfica táctil (GUI)
- Guante inteligente con reconocimiento autónomo en ESP32
- Integración de cámara, micrófono, altavoz y pantallas
- Uso de redes neuronales entrenadas con un dataset propio
- Arquitectura modular y escalable


---

## Hardware Utilizado

- **Raspberry Pi 5:** procesamiento principal y visión por computadora  
- **Raspberry Pi 3:** procesamiento de audio y control de periféricos  
- **ESP32:** procesamiento del guante inteligente  
- **Cámara:** lectura del lenguaje de señas  
- **Pantallas táctiles:** interfaz de usuario  
- **LCD 16x2:** visualización de subtítulos para la persona sordomuda  
- **Micrófono USB:** entrada de audio  
- **Altavoz:** salida de audio sintetizado  
- **Flex sensors:** detección de posición de los dedos  
- **IMU (acelerómetro + giroscopio):** detección del movimiento de la mano  

NOTA: El sistema está diseñado modularmente para poder agregar nuevos gestos o vocabulario.

---

##  Estructura del Repositorio
```text
sistema-embebido-lsm/
│
├── vision/
│ ├── collect_data.py # Captura de muestras de señas
│ ├── prepare_dataset.py # Preparación del dataset
│ ├── train_classifier_mlp.py # Entrenamiento de la red neuronal
│ ├── run_inference.py # Inferencia en tiempo real
│ ├── tvtry1.py # Reconocimiento visión + audio
│ └── txvoicbt05.py # Visión + audio + interfaz gráfica
│
├── glove/
│ └── reconocimientoguante.c # Reconocimiento de palabras con guante
│
├── audio_micro_lcd/
│ └── micro_lcd.py # Voz y despliegue de guante en LCD
│
├── docs/
│ └── arquitectura_sistema.png # Diagramas y documentación
│
├── README.md
├── requirements.txt
└── .gitignore


---

## SW Utilizado

- Python  
- C  
- OpenCV  
- Scikit-learn / Redes neuronales MLP  
- Procesamiento de señales de audio  
- Raspberry Pi OS  
- ESP32  

El sistema utiliza una red neuronal tipo **MLP (Multi-Layer Perceptron)** entrenada con imágenes propias obtenidas mediante:

- `collect_data.py` → captura imágenes y landmarks
- `prepare_dataset.py` → normaliza y genera el dataset
- `train_classifier_mlp.py` → entrena el modelo final

La inferencia de señas se realiza con:

- `run_inference.py` (deteccion por vision RPi5)
- `micro_lcd.py` (deteccion por guante + micrófono RPi3)
---

##  Alcance Actual

- Reconocimiento limitado al **abecedario en Lengua de Señas Mexicana**
- Conjunto reducido de palabras reconocidas mediante el guante
- Entrenamiento supervisado con dataset propio

---

##  Impacto Social

Este proyecto busca **reducir las barreras de comunicación** entre personas sordomudas y oyentes, promoviendo la inclusión y la accesibilidad mediante el uso de sistemas embebidos, visión por computadora y aprendizaje automático.

---

##  Autor
Violeta Daniela Ávila García, Maria Fernanda Cruz González, Valeria Fernanda García Bustos, Sara Sofía Hernández Valdez, Mariana Claudia Villalobos Cortés

Estudiantes de Ingeniería en Robótica y Sistemas Digitales
Tecnológico de Monterrey, México
Proyecto desarrollado como sistema embebido con enfoque social y educativo.


