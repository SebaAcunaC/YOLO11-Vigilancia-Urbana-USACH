# Optimización de Arquitecturas YOLO11 para Vigilancia Urbana - USACH

Este repositorio contiene el desarrollo de un sistema de detección de personas y optimización de rendimiento para aplicaciones de vigilancia en tiempo real.  
El proyecto se enfoca en superar el cuello de botella del procesamiento en **video 4K**, mediante un análisis multiresolución que permita identificar el equilibrio óptimo entre precisión y rendimiento.

---

# Material Completo del Proyecto

Debido al tamaño de algunos archivos experimentales (videos, pesos del modelo, resultados de entrenamiento y grabaciones semanales), el material completo del proyecto se encuentra disponible en el siguiente repositorio en Google Drive:

**Repositorio en Google Drive**  
https://drive.google.com/drive/folders/1JdyCxNtXBqZpZ1PeW9EmyceepfesznmW?usp=sharing

El contenido incluye:

- Pesos entrenados del modelo YOLO11
- Resultados de entrenamiento
- Videos de pruebas del sistema
- Grabaciones semanales del avance del proyecto
- Resultados experimentales adicionales

---

# Especificaciones Técnicas

* **Hardware:** GPU NVIDIA Tesla T4 (Google Colab)  
* **Framework:** Ultralytics YOLO11 (versión Nano optimizada para baja latencia)  
* **Entorno:** Python 3.10+ con persistencia en Google Drive  

---

# Comparativa de Entrenamiento (YOLO11 vs YOLOv8)

![Gráfica Comparativa](Semana-3-Comparativa/grafica_comparativa_final.png)

*Figura 1: Evolución de precisión y pérdida durante el entrenamiento de los modelos evaluados.*

---

# Resultados Destacados (Hito Semana 5)

Se logró una mejora de rendimiento de aproximadamente **1400%** mediante la optimización de la resolución de entrada.

* **Línea Base (4K):** 7.10 FPS  
* **Configuración Optimizada (640p):** 107.03 FPS  
* **Sweet Spot:** Se identificó **640p** como la resolución óptima que equilibra precisión y velocidad para aplicaciones de vigilancia urbana en tiempo real.

---

# Estructura del Proyecto (Evolución Semanal)

Para garantizar la **reproducibilidad del proyecto**, el desarrollo se organizó de forma incremental en cinco etapas:

* **[Semana 1: Prueba](./Semana-1_Entrenamiento)**  
  Validación inicial del modelo YOLO11 y pruebas de funcionamiento en el entorno de ejecución.

* **[Semana 2: Entrenamiento](./Semana-2-Entrenamiento)**  
  Fine-tuning inicial del modelo YOLO11n utilizando un dataset obtenido desde Roboflow.

* **[Semana 3: Comparativa](./Semana-3-Comparativa)**  
  Benchmark directo entre YOLO11 y YOLOv8 para evaluar precisión y rendimiento.

* **[Semana 4: Validación 4K](./Semana-4-Benchmarking)**  
  Identificación del cuello de botella computacional al procesar video en resolución 4K.

* **[Semana 5: Optimización](./Semana-5-Optimizacion)**  
  Análisis multiresolución para determinar el mejor trade-off entre latencia y precisión.

---

# Resultados Finales de Benchmarking (Master Notebook)

| Arquitectura | Resolución | FPS Reales | Latencia Total |
| :--- | :--- | :--- | :--- |
| **YOLO11n (USACH)** | 320p | **25.09** | 39.8 ms |
| **YOLOv8n (Base)** | 320p | 23.02 | 43.4 ms |
| **Faster R-CNN (Legacy)** | 640p | 0.19 | 5209.5 ms |

---

# Análisis Multi-resolución (Hito Semana 5)

A continuación se muestran ejemplos de detección tras el ajuste de **stride 32** y la evaluación de distintas resoluciones:

* **Alta Fidelidad (1088p)**  
  [Ver captura](./Semana-5-Optimizacion/1088p.png)

* **Balance Ideal (640p)**  
  [Ver captura](./Semana-5-Optimizacion/640p.png)

* **Máximo Rendimiento (320p)**  
  [Ver captura](./Semana-5-Optimizacion/320p.png)

---

# 📄 Documento del Proyecto

El desarrollo completo del proyecto, incluyendo metodología, experimentos y análisis de resultados, se encuentra documentado en el **mini-paper académico incluido en este repositorio**.
