# Automated Microscopy Cell Counter & Morphometric Analyzer

An automated biomedical computer vision pipeline designed to count, segment, and extract morphological metrics (surface area, perimeter, and equivalent circular diameter) from microscopic blood cell imagery. 

Built using **Python, OpenCV, NumPy, Pandas, and Matplotlib**, this tool replaces manual, error-prone visual cell counting with a fast, reproducible digital pathology workflow.

---

## 📸 Visual Summary & Dashboard

![Detection Dashboard](output/detection_dashboard.png)

*Figure 1: Automated 4-panel diagnostic summary showing (1) Original RGB microscopy image, (2) Noise-filtered Otsu thresholded binary mask, (3) Annotated cell boundaries with ID tracking, and (4) Cell diameter distribution histogram.*

---

## 🎯 Clinical Significance & Problem Statement

In clinical pathology and biomedical research, determining total cell counts and size distributions (e.g., Red Blood Cell Count, White Blood Cell Differential) is vital for diagnosing conditions like **anemia, leukemia, and systemic infections**:

* **Traditional Manual Counting:** Time-consuming, subjective, prone to eye fatigue, and inconsistent across different lab technicians.
* **Automated Computer Vision Solution:** Provides 100% deterministic, high-throughput analysis in seconds, generating reproducible morphometric data exported directly to standardized CSV reports.

---

## 🛠️ Key Technical Features

* **Adaptive Image Binarization:** Employs **Otsu’s Thresholding** to automatically derive the optimal grayscale cutoff for separating cell bodies from background illumination.
* **Morphological Noise Filtering:** Implements kernel-based opening operations (Erosion followed by Dilation) to eliminate sub-cellular debris and imaging noise.
* **Contour Filtering & Size Cutoffs:** Filters out artifacts below a 50-pixel minimum area threshold to isolate true cellular structures.
* **Automated Morphometric Extraction:** Calculates surface area, perimeter, and equivalent circular diameter using vector math (`NumPy`).
* **Data Reporting & Visualization:** Automatically exports structured measurements to `cell_measurements.csv` and renders a 4-panel diagnostic dashboard with cell size histograms (`Matplotlib`).

---

## 📊 Sample Output Data

The pipeline generates a structured CSV report containing individual metric records for every detected cell:

| Cell_ID | Area_Pixels | Perimeter_Pixels | Equivalent_Diameter |
| :---: | :---: | :---: | :---: |
| **1** | 452.0 | 78.42 | 23.99 |
| **2** | 612.5 | 91.14 | 27.93 |
| **3** | 388.0 | 72.10 | 22.23 |
| **4** | 504.0 | 82.35 | 25.33 |

---

## 🚀 Getting Started

### Prerequisites & Installation

Clone the repository and install the required dependencies:

```bash
git clone [https://github.com/your-username/bme-cell-counter.git](https://github.com/your-username/bme-cell-counter.git)
cd bme-cell-counter
pip install opencv-python numpy pandas matplotlib
