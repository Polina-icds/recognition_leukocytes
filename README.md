# Recognition of Leukocytes: Classic ML vs. CNN

**Master‘s Thesis | HSE University | Applied Mathematics & Computer Science**

## 📌 Overview

This project compares two approaches to leukocyte (white blood cell) classification in medical imaging:

- **SVM (Support Vector Machine)** – classic machine learning with hand-crafted morphological features
- **CNN (Convolutional Neural Network)** – deep learning, InceptionV3‑based

**Key research question:** Can a classic model outperform a neural network on medium‑sized medical image data?

**Main result:**  
✅ SVM achieved **94% overall accuracy** and significantly outperformed CNN on **blast cell detection** (95% vs 81%).  
Since blasts are the primary marker for leukemia, this result has direct clinical relevance.

---

## 🧬 Medical context

Leukocyte classification is critical for hematological diagnostics. Three cell types were analyzed:

| Cell type | Characteristics | Clinical importance |
|-----------|----------------|----------------------|
| **Blasts** | Immature precursor cells | Key marker for leukemia |
| **Lymphocytes** | Round nucleus, little cytoplasm | Mature immune cells |
| **Monocytes** | Large, kidney‑shaped nucleus | Phagocytic cells |

---

## 📊 Dataset

- **Total images:** 84,958
- **Split:** train / test

| Class       | Train | Test |
|-------------|-------|------|
| Blasts      | 784   | 347  |
| Lymphocytes | 4,495 | 1,969|
| Monocytes   | 1,644 | 647  |

> The dataset reflects a real‑world clinical distribution (mature cells are naturally more abundant).

---

## ⚙️ Methods

### SVM (Classic approach)
- **Features:** morphological + textural (nucleus area, segment count, color components)
- **Top features per cell type:**
  - **Monocytes** – NODG (green component segmentation) → reflects kidney‑shaped nucleus
  - **Blasts** – NuclEuFFDist → captures shape variability of immature cells
  - **Lymphocytes** – Narea → nucleus occupies most of the cell

### CNN (Deep Learning)
- **Architecture:** InceptionV3, fine‑tuned on the same dataset
- **Approach:** automatic feature extraction, no manual engineering

---

## 📈 Results

**Overall accuracy:** 94% (±0.01)

### CNN results (test set)

| Class       | Accuracy |
|-------------|----------|
| Blasts      | 81.6%    |
| Lymphocytes | 95.4%    |
| Monocytes   | 94.3%    |

### Comparison: SVM vs CNN

| Class       | SVM (accuracy) | CNN (accuracy) |
|-------------|----------------|----------------|
| Monocytes   | 91%            | 94%            |
| **Blasts**  | **95%**        | **81%**        |
| Lymphocytes | 96%            | 95%            |

**Interpretation:**  
- SVM is significantly better on blast detection (+14 percentage points) – the most clinically important class.
- CNN slightly outperforms SVM on monocytes but requires much more data for full potential.
- For medium‑sized medical datasets with clear morphological features, **classic ML can be more reliable**.

---

## 🚀 How to reproduce

1. **Clone** this repository  
2. **Install dependencies** (Python 3.8+):
3. **Run Jupyter notebooks** (order doesn‘t matter, they are independent)

> The original image dataset is not included due to size and institutional policies.

---

## 📬 Contact

**Polina Guseva** – [pguseva26@gmail.com] | [LinkedIn](https://linkedin.com/in/polina-guseva)

**GitHub:** [Polina-icds/recognition_leukocytes](https://github.com/Polina-icds/recognition_leukocytes)