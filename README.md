# 📐 SVD — Singular Value Decomposition
### A Complete Interactive Guide for Data Science

> **A = U × Σ × Vᵀ** — Breaking matrices into beautiful, meaningful pieces.

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

---

## 📖 Overview

This repository contains two learning resources for **Singular Value Decomposition (SVD)** — one of the most fundamental and powerful techniques in data science and linear algebra:

| File | Format | Description |
|------|--------|-------------|
| `SVD_Guide.docx` | Word Document | Comprehensive step-by-step written guide with worked examples |
| `SVD_Interactive.html` | Interactive Web Page | Visual, animated, browser-based SVD explorer |

Both resources cover the same material but in different formats — use whichever fits your learning style.

---

## 🗂️ What's Covered

```
SVD Guide
├── 1. What is SVD?             — Concept, intuition, real-world analogy
├── 2. The Three Matrices       — U, Σ, Vᵀ explained with properties
├── 3. Step-by-Step Computation — Full hand-calculation on a 2×2 matrix
├── 4. Truncated SVD            — Low-rank approximation & explained variance
├── 5. Real-World Example       — Image compression walkthrough
├── 6. Python Code              — NumPy, scikit-learn, image compression
├── 7. Applications             — Where SVD is used in the real world
└── 8. Quick Reference          — Cheat sheet summary table
```

---

## 🌐 Interactive HTML Guide

Open `SVD_Interactive.html` directly in any browser — **no server, no install required**.

### Features

- 🎯 **Live SVD Calculator** — Enter any 2×2 matrix, get U, Σ, Vᵀ computed instantly
- 📊 **Variance Bar Chart** — Animated bars showing how much each singular value explains
- 🧮 **Step-by-Step Timeline** — Numbered walkthrough with syntax-highlighted math
- 🎨 **Color-coded Matrix Equation** — U, Σ, Vᵀ visually distinguished at a glance
- ✨ **Scroll Animations** — Smooth reveal effects as you read through
- 📋 **Copy-ready Python Code** — Syntax-highlighted blocks for NumPy & sklearn

### Quick Start

```bash
# Clone the repo
git clone https://github.com/your-username/svd-guide.git
cd svd-guide

# Open in browser (no install needed)
open SVD_Interactive.html          # macOS
start SVD_Interactive.html         # Windows
xdg-open SVD_Interactive.html      # Linux
```

---

## 🔢 The Math — At a Glance

Any matrix **A** (m × n) can be decomposed as:

```
A  =  U  ×  Σ  ×  Vᵀ
```

| Matrix | Size  | Property        | Meaning                              |
|--------|-------|-----------------|--------------------------------------|
| **U**  | m × m | Orthonormal cols | Directions in row space              |
| **Σ**  | m × n | Diagonal, σ ≥ 0  | Importance/weight of each direction  |
| **Vᵀ** | n × n | Orthonormal rows | Directions in column space           |

**Key relationships:**
- Singular values: `σᵢ = √λᵢ` (square root of eigenvalues of AᵀA)
- Sorted order: `σ₁ ≥ σ₂ ≥ ... ≥ 0`
- Explained variance: `σᵢ² / Σσ² × 100%`

---

## 🐍 Python Quick Reference

```python
import numpy as np

A = np.array([[3, 1],
              [1, 3]])

# Full SVD
U, sigma, Vt = np.linalg.svd(A)

print("U:", U.round(3))
print("Singular values:", sigma.round(3))   # [4. 2.]
print("Vt:", Vt.round(3))

# Reconstruct A
A_back = U @ np.diag(sigma) @ Vt
print("Reconstructed:", A_back.round(3))    # matches original
```

```python
from sklearn.decomposition import TruncatedSVD

# Truncated SVD — keep only top k components
svd = TruncatedSVD(n_components=5)
A_reduced = svd.fit_transform(A)

print("Variance explained:", svd.explained_variance_ratio_)
```

---

## 🎯 Applications

| Application | How SVD Helps |
|---|---|
| 🖼️ **Image Compression** | Keep top-k singular values → smaller file, similar visual quality |
| 🎬 **Recommender Systems** | Matrix factorization of user-item ratings (Netflix, Spotify) |
| 📝 **NLP / LSA** | Find hidden topics in document-term matrices |
| 🔇 **Noise Reduction** | Discard small singular values → cleaner signal |
| 📊 **PCA** | PCA is SVD on mean-centered data — same math, different framing |
| 🔬 **Pseudoinverse** | Solve least-squares problems via `A⁺ = V × Σ⁺ × Uᵀ` |

---

## 📁 Repository Structure

```
svd-guide/
├── README.md               ← You are here
├── index.html    ← Interactive browser guide (open directly)
└── SVD_Guide.docx          ← Printable Word document guide
```

---

## 🎓 Who This Is For

- **Students** studying linear algebra, machine learning, or data science
- **Engineers** who want an intuitive refresher on SVD
- **Anyone** who prefers learning visually and interactively

---

## 📚 Further Reading

- [NumPy SVD documentation](https://numpy.org/doc/stable/reference/generated/numpy.linalg.svd.html)
- [scikit-learn TruncatedSVD](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.TruncatedSVD.html)
- [Wikipedia — Singular Value Decomposition](https://en.wikipedia.org/wiki/Singular_value_decomposition)

---

## 📄 License

MIT License — free to use, share, and adapt with attribution.

---

<p align="center">Made for the Data Science & Engineering community 🚀</p>