# color-recognition

An interactive Python-based tool designed to identify and classify the color of a specific pixel within an uploaded image. Built specifically for execution in **Google Colab**, this tool downloads a comprehensive color dataset from Kaggle, computes average RGB profiles for various color classes, and maps sampled pixel coordinates to the closest matching color name using distance metrics.

---

## Features

* **Automated Dataset Integration**: Seamlessly downloads and caches the `color-dataset-for-color-recognition` dataset via `kagglehub`.
* **Dynamic Class Profiling**: Automatically traverses directory structures to compute average representative `(R, G, B)` values across multiple sample images per color class.
* **Euclidean/Manhattan Distance Matching**: Evaluates pixel color values against trained class profiles to find the closest color match.
* **Colab-Optimized Interface**: Bypasses local GUI window restrictions by allowing users to input `x, y` pixel coordinates directly with real-time visual annotations and swatch previews using `cv2_imshow`.

---

## Supported Color Classes

The tool evaluates and classifies pixels into the following standard categories:
* `black`
* `blue`
* `brown`
* `green`
* `grey` / `gray`
* `orange`
* `red`
* `violet`
* `white`
* `yellow`

---

## Prerequisites & Dependencies

The project relies on standard computer vision and data manipulation libraries:

* Python 3
* `opencv-python` (`cv2`)
* `pandas`
* `kagglehub`
* `google.colab`

---

## Getting Started & Usage

1. **Open in Google Colab**: Upload or open the provided Jupyter notebook (`.ipynb`) in Google Colab.
2. **Install & Import**: Run the initial code blocks to load the required libraries (`cv2`, `pandas`, `kagglehub`, etc.).
3. **Download Dataset**: The script will automatically fetch and cache the training dataset from Kaggle:
   ```python
   os.environ["KAGGLEHUB_CACHE"] = "/content/my_datasets"
   downloaded_path = kagglehub.dataset_download("adikurniawan/color-dataset-for-color-recognition")
