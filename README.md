# Embedded LSM Communication System

## Descripción General

Este proyecto implementa un sistema embebido diseñado para facilitar la comunicación entre personas sordomudas y oyentes mediante el uso de visión por computadora, sensores flexibles y aprendizaje automático. El sistema traduce el Lenguaje de Señas Mexicano (LSM) a texto y audio en tiempo real, y también convierte voz hablada en texto para la persona sordomuda.

Actualmente, el sistema reconoce el abecedario en LSM y funciona mediante dos módulos principales:

- **Raspberry Pi 5 (módulo maestro):** encargado de interpretar señas mediante la cámara, reproducir audio, procesar voz y mostrar información en una pantalla touch y una LCD 16x2.
- **Guante inteligente con ESP32:** equipado con sensores de flexión y un IMU (acelerómetro + giroscopio) para detectar movimientos de la mano y enviar las señas reconocidas.

---

## Características del Sistema

- Traducción de señas LSM a texto
- Síntesis de voz para leer en altavoz lo interpretado
- Reconocimiento de voz con transcripción visual para usuarios sordomudos
- Interfaz gráfica táctil (GUI) integrada
- guante con sensores para reconocimiento autónomo en ESP32
- Integración de cámara, micrófono, altavoz y pantalla
- Uso de redes neuronales entrenadas con dataset propio

---

## Hardware Utilizado

=> Raspberry Pi 5: Procesamiento principal y visión 
=> ESP32: Procesamiento del guante 
=> Cámara: Lectura del lenguaje de señas 
=> LCD 16x2: Mostrar texto para oyentes 
=> Pantalla touch: Interfaz para usuario sordomudo 
=> Micrófono USB: Entrada de audio 
=> Altavoz: Síntesis de voz 
=> Flex sensors: Detección de dedos 
=> IMU (Acelerómetro + Giroscopio): Movimiento de mano

NOTA: El sistema está diseñado modularmente para poder agregar nuevos gestos o vocabulario.

---

##  Estructura del Repositorio

