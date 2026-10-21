<div align="center">

# 🛰️ Hyperspectral Anomaly Detection Datasets

**A curated directory of publicly shared hyperspectral image datasets for anomaly detection research and benchmarking.**

*AVIRIS · Airport–Beach–Urban (ABU) · HYDICE · Salinas*

[![Datasets](https://img.shields.io/badge/dataset%20collections-5-2563eb)](#dataset-directory)
[![ABU Scenes](https://img.shields.io/badge/ABU%20scenes-13-0d9488)](#dataset-directory)
[![Format](https://img.shields.io/badge/common%20format-MATLAB%20.mat-7c3aed)](#getting-started)
[![Contributions](https://img.shields.io/badge/contributions-welcome-16a34a)](https://github.com/NomanShahRaza/hyperspectral_anomaly_datasets/issues)

[**📂 Explore Datasets**](#dataset-directory) · [**🚀 Getting Started**](#getting-started) · [**📚 Cite This Research**](#citation) · [**🧠 Detection Algorithms**](https://github.com/NomanShahRaza/hyperspectral_anomaly_detection_algorithms)

</div>

---

## 📖 Overview

Hyperspectral anomaly detection aims to identify pixels or small regions whose spectral signatures differ from the surrounding background. Publicly shared scenes and, where available, reference masks help researchers develop, evaluate, and compare detection methods.

This repository indexes publicly available datasets used in our [2022 comparative study](https://doi.org/10.1080/17538947.2022.2146770), which evaluated **22 anomaly detection algorithms across 17 datasets**. It is a **dataset directory**, not a re-hosted dataset package. Download files from the linked providers, and consult their repositories for acquisition details, preprocessing, usage conditions, and citations.

<a id="dataset-directory"></a>
## 📂 Dataset Directory

| Dataset | Scenes / variants | What you'll find | Dataset access |
|:---|:---|:---|:---|
| **🛩️ AVIRIS-I** | AVIRIS example (San Diego) | Hyperspectral scene and aircraft-anomaly ground truth in the linked research repository | [View dataset ↗](https://github.com/huyanning/Hyperspectral-Anomaly-Detection) |
| **🏙️ ABU (Airport–Beach–Urban)** | **Airport I–IV** (4) · **Beach I–IV** (4) · **Urban I–V** (5) | 13 anomaly-detection scenes with corresponding reference maps | [Browse all 13 scenes ↗](https://github.com/sxt1996/Airport-Beach-Urban-ABU) |
| **🛰️ AVIRIS-II** | AVIRIS collection referenced in the original dataset list | Dataset resources associated with the AED research implementation; inspect its `Data` folder for available files | [Open AED data folder ↗](https://github.com/yousefan/AED-algorithm/tree/master/Data) |
| **🚗 HYDICE Urban Area** | Urban anomaly scene | HYDICE hyperspectral image and reference anomaly map | [View dataset ↗](https://github.com/sxt1996/HYDICE) |
| **🌾 Salinas** | Synthetic Salinas anomaly-detection example | `Salians_syn.mat` and `Salians_syn_gt.mat` as published with LSUNRSORAD / LSAD-CR-IDW code | [View dataset files ↗](https://github.com/zephyrhours/Hyperspectral-Anomaly-Detection-LSUNRSORAD-and-LSAD-CR-IDW-) |

> [!NOTE]
> **Dataset names are retained from the original catalogue.** AVIRIS-I / AVIRIS-II are catalogue labels, not official AVIRIS sensor model names. The linked Salinas resource is specifically a *synthetic anomaly-detection example*.

<a id="getting-started"></a>
## 🚀 Getting Started

1. **Choose a dataset** from the table and open its provider repository.
2. **Download the scene and its ground-truth map**, when provided. GitHub files can usually be downloaded individually from their file pages.
3. **Inspect the data structure** before benchmarking. Band selection, image shape, normalization, and mask conventions can differ between sources.
4. **Apply consistent evaluation settings** when comparing anomaly detectors across datasets.

### 🐍 Inspect a MATLAB dataset with Python

Many of the linked resources provide `.mat` files. The following snippet shows their variable names and dimensions without assuming that every file uses the same keys:

```bash
python -m pip install scipy
```

```python
from scipy.io import loadmat

# Replace with the path to a downloaded .mat file.
contents = loadmat("data/abu-airport-1.mat")

for name, value in contents.items():
    if not name.startswith("__") and hasattr(value, "shape"):
        print(f"{name}: {value.shape}")
```

Some MATLAB v7.3 files require an HDF5-compatible reader rather than `scipy.io.loadmat`.

## 🔗 Related Resources

- **[Hyperspectral Anomaly Detection Algorithms](https://github.com/NomanShahRaza/hyperspectral_anomaly_detection_algorithms)** — a companion catalogue of classical and deep-learning detection approaches.
- **[AED research implementation](https://github.com/yousefan/AED-algorithm)** — the research repository originally referenced for AVIRIS-II and HYDICE data.

<a id="citation"></a>
## 📚 Citation

The datasets listed in this repository were used in our comparative study of **22 hyperspectral anomaly detection algorithms evaluated on 17 publicly available datasets**:

> Shah, N. R., Maud, A. R. M., Bhatti, F. A., Ali, M. K., Khurshid, K., Maqsood, M., & Amin, M. (2022). **Hyperspectral anomaly detection: a performance comparison of existing techniques.** *International Journal of Digital Earth, 15*(1), 2078–2125. [https://doi.org/10.1080/17538947.2022.2146770](https://doi.org/10.1080/17538947.2022.2146770)

<details>
<summary><strong>📄 Copy BibTeX citation</strong></summary>

```bibtex
@article{shah2022hyperspectral,
  author  = {Shah, Noman Raza and Maud, Abdur Rahman M. and Bhatti, Farrukh Aziz and Ali, Muhammad Khizer and Khurshid, Khurram and Maqsood, Moazam and Amin, Muhammad},
  title   = {Hyperspectral anomaly detection: a performance comparison of existing techniques},
  journal = {International Journal of Digital Earth},
  volume  = {15},
  number  = {1},
  pages   = {2078--2125},
  year    = {2022},
  doi     = {10.1080/17538947.2022.2146770}
}
```

</details>

**When to cite this paper:** Please cite the study if you use this repository to reproduce, compare with, or build upon the experimental evaluation reported there.

**Dataset attribution:** These datasets were originally collected and shared by their respective providers. If you use the data, also cite the relevant original dataset publications and follow the providers' licensing or usage requirements. This repository does not claim ownership of the underlying data.

### 🤝 Contributing

Found a broken link or have a well-documented hyperspectral anomaly-detection dataset to add? [Open an issue](https://github.com/NomanShahRaza/hyperspectral_anomaly_datasets/issues) or [submit a pull request](https://github.com/NomanShahRaza/hyperspectral_anomaly_datasets/pulls). Include a dataset source, citation, file format, and ground-truth availability where possible.

---

<div align="center">

*Maintained as a community-friendly reference for hyperspectral anomaly detection research.*

</div>
