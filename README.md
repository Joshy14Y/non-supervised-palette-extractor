# 🎨 Chromatic Clustering for Artistic Palette Extraction

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

An **Unsupervised Machine Learning pipeline** designed to extract and analyze color palettes from artworks using **multiple clustering paradigms**. The project compares **centroid-based, density-based, and mode-seeking algorithms** to study how different assumptions about color geometry and distribution shape the resulting palettes.

Rather than treating clustering as a black box, the pipeline emphasizes **algorithmic interpretability**, showing how internal model mechanics are reflected directly in the visual and quantitative results.

---

## 🎯 Project Motivation

Color in painting is not continuous in intent, even when it appears continuous perceptually. Artists work with **limited pigments, compositional constraints, and stylistic conventions**, which impose structure on the color space.

This project explores whether unsupervised clustering algorithms can:

- recover dominant chromatic structures,
- distinguish between **simple, geometric, and highly complex compositions**, and
- expose how different clustering assumptions (global centroids, density, local modes) interpret the same artwork differently.

By applying the same pipeline across diverse paintings and styles, the project performs a form of **computational color analysis**, bridging machine learning, visual perception, and art interpretation.

---

## 🚀 Key Features

- **Multi-Algorithm Clustering**
  - **K-Means** (centroid-based, global partitioning)
  - **DBSCAN** (density-based, structure-driven clustering)
  - **Mean Shift** (mode-seeking, local density estimation)

- **Automatic Model Selection**
  - Optimal configurations selected via the **Silhouette Coefficient**
  - Enables objective comparison across algorithms and artworks

- **Style-Sensitive Behavior**
  - Differentiates between:
    - paintings with few dominant color fields,
    - works with strong geometric segmentation,
    - highly fragmented, high-entropy compositions

- **Modular, Reproducible Pipeline**
  - `FeatureExtractor`: image preprocessing and pixel sampling
  - `ColorGrouper`: clustering and model evaluation
  - `PaletteReporter`: visualization, palette rendering, and validation

- **Advanced Visualization**
  - Extracted palettes with hex codes
  - Silhouette curves for model selection
  - **t-SNE projections** for visual validation of cluster structure

---

## 📊 Technical Observations

The experiments reveal consistent relationships between **artistic structure** and **algorithmic behavior**:

| Artwork Type | Typical Outcome | Algorithmic Interpretation |
|--------------|----------------|----------------------------|
| Minimal / Dominant Color Fields | Low optimal *k* | Few well-separated global modes; ideal for K-Means |
| Geometric / Flat Color Regions | Moderate *k* | Stable centroid structure with clear boundaries |
| Highly Fragmented / Textured | High *k* (Mean Shift) | Many local density maxima; micro-structure dominates |
| Sparse Color Distributions | Very low effective clusters (DBSCAN) | Density-driven collapse into dominant modes |

These results show that clustering outputs are not just palettes, but **diagnostics of visual structure**.

---

## 🛠️ Installation & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/color-clustering-art.git
   cd color-clustering-art
