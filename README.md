# 🎨 Palette Extractor

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

**Palette Extractor** es un pipeline avanzado de **Aprendizaje No Supervisado** diseñado para la deconstrucción cromática de obras de arte. Mediante una comparativa multialgoritmo, el sistema identifica la esencia tonal de cada pieza, permitiendo una transición fluida entre el análisis de arte tradicional y la abstracción moderna.

---

## 🔬 Enfoque Técnico: Comparativa Multialgoritmo

El núcleo del proyecto evalúa tres arquitecturas de clustering para determinar cuál representa mejor la estructura visual de la obra:

* **K-Means (Centroides):** Optimizado mediante **Silhouette Analysis** ($k \in [2, 10]$). Ideal para identificar contrastes estructurales dominantes y colores base.
* **HDBSCAN (Densidad):** Agrupamiento espacial que identifica clústeres de forma orgánica, gestionando el ruido visual sin requerir un número de clústeres predefinido.
* **MeanShift (Modas):** Localiza picos de intensidad cromática, capturando con alta fidelidad los degradados y las transiciones sutiles de color.

## 🚀 Características Principales

* **Optimización Dinámica:** Selección automática de hiperparámetros basada en métricas de cohesión y separación (*Silhouette Score*).
* **Visualización Científica:** Proyección de píxeles mediante **t-SNE** para validar matemáticamente la separabilidad de los colores extraídos.
* **Arquitectura Limpia:** Implementación modular a través de la clase `PaletteReporter`, enfocada en código atómico y autodocumentado.
* **Análisis de Complejidad:** Diferenciación automática entre composiciones minimalistas y escenas de alta entropía visual.

## 📊 Hallazgos Técnicos

| Algoritmo | Fortalezas | Caso de Uso Ideal |
| :--- | :--- | :--- |
| **K-Means** | Eficiencia y estructura clara. | Obras con bloques de color definidos. |
| **HDBSCAN** | Estabilidad ante variaciones de densidad. | Arte con texturas y patrones complejos. |
| **MeanShift** | Granularidad en micro-tonos. | Captura de gradientes y transiciones suaves. |

## 🛠️ Instalación y Uso

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/Joshy14Y/palette-extractor.git](https://github.com/Joshy14Y/palette-extractor.git)
   cd palette-extractor