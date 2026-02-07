# 🎨 Ukiyo-e Palette Generator

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

An **Unsupervised Machine Learning** pipeline designed to chromatically deconstruct Japanese art (*Ukiyo-e*). It uses **Dynamic Clustering (K-Means)** optimized via Silhouette analysis to extract color palettes that respect both visual complexity and historical woodblock printing techniques.

---

## 🇯🇵 Project Motivation

*Ukiyo-e* art (Edo period) was produced by layering inked woodblocks. Unlike oil painting, this implies a **discrete nature** of color.

This project uses clustering algorithms to perform **"reverse engineering"** on these artworks, attempting to mathematically recover the original inks used by masters like *Hiroshige* and *Kuniyoshi*, distinguishing between simple compositions (landscapes) and high-entropy scenes (battles/mythology).

## 🚀 Key Features

* **Dynamic K Selection ($k \in [5, 10]$):** The model does not use a fixed number of colors. It iteratively evaluates the image structure and selects the optimal $K$ based on the **Silhouette Coefficient**.
* **Visual Entropy Analysis:** Automatically differentiates between minimalist styles (*Fukei-ga*) and chaotic styles (*Musha-e*).
* **Modular Pipeline:** Code structured in Classes (`FeatureExtractor`, `ColorGrouper`, `PaletteReporter`) with Type Hinting.
* **Advanced Visualization:** Palette generation, image segmentation, and dimensionality reduction using **t-SNE**.

## 📊 Technical Findings

The model revealed patterns consistent with Japanese art history:

| Style | Example Work | Detected K | Model Interpretation |
| :--- | :--- | :---: | :--- |
| **Landscape (Fukei-ga)** | *Hiroshige* | **5 - 6** | Detected "economy of means". Few, very compact and well-separated clusters, ideal for representing large gradient areas (*Bokashi*). |
| **Complex (Musha-e)** | *The Magic Toads* | **9** | **Anomaly Detection.** Faced with high structural complexity (textile patterns, textures), the model scaled to $K=9$ to prevent information loss. |

## 🛠️ Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Joshy14Y/ukiyo-e-palette-generator.git](https://github.com/Joshy14Y/ukiyo-e-palette-generator.git)
    cd ukiyo-e-palette-generator
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **File Structure:**
    Ensure your images are in the correct folder:
    ```text
    ├── images/             # Place your 10 images here
    ├── p1.ipynb            # Main notebook with the pipeline
    ├── requirements.txt    # Dependencies
    └── README.md           # Documentation
    ```

4.  **Run:**
    Open `p1.ipynb` in Jupyter Lab or VS Code and execute the cells sequentially.

## 📦 Tech Stack

* **Core:** Python 3
* **ML & Data:** `scikit-learn` (KMeans, Silhouette Score, t-SNE), `numpy`
* **Image Processing:** `Pillow` (PIL)
* **Visualization:** `matplotlib`

## 📄 License

This project was developed for academic purposes as part of an Unsupervised Machine Learning course.

---
Developed by Joshua Sancho