# 🌲 Fire-Ready Forests Data Challenge – Team Agni Astra

Welcome to the repository for **Team Agni Astra**'s submission to the **Fire-Ready Forests Data Challenge** hosted by the **National Data Platform**. Our aim was to build a robust and interpretable machine learning pipeline for classifying forest trees in California across three biological levels:

1. **Plant Functional Type (PFT)**
2. **Genus**
3. **Species**

We used ecological, morphological, and spatial features to train a hierarchical ensemble of classifiers that achieved strong predictive performance across all levels.

---

## 📁 Repository Structure
```
├── data/               # Processed and merged datasets (FIA + REF_SPECIES)
├── Images/             # All project-related figures and visualizations
├── final_NB.ipynb            # Final pipeline notebook (run this)
├── plots.ipynb         # Exploratory plots and feature analyses
├── requirements.txt    # Required Python packages
├── .gitattributes      # Git LFS tracking config
├── README.md           # This file
```

---

## ⚠️ Git LFS Required
This repository uses **[Git Large File Storage (LFS)](https://git-lfs.github.com/)** to handle large files like `CA_TREE.csv`.

**Before cloning**, ensure LFS is installed and initialized:

```bash
# One-time setup (if you haven't already)
git lfs install
```

if you are running on a conda environment, initialize new environment with the following code:

```bash
conda create -n "env-name" python=3.11

conda activate env-name
```
If not on conda, then you can directly skip to the below steps

```bash

# Clone the repo
git clone <repo-url>
cd <repo-name>

pip install -r requirements.txt
```
If you don't set up Git LFS, large files like `data/CA_TREE.csv` will not download correctly.

---

## 🚀 Pipeline Overview
We implemented a hierarchical stacking ensemble pipeline to classify:

- 🌿 **PFTs** using tree structure, location, and ecological data
- 🌲 **Genus** using all of the above + predicted PFT
- 🌳 **Species** using all of the above + predicted Genus

---

## 🔧 Preprocessing Steps
- Merged FIA and REF_SPECIES datasets
- Dropped highly correlated features (e.g., BasalA)
- Filtered by ecological zones (`ECOSUBCD`)
- One-hot encoded categorical variables
- Handled missing values
- Converted units (e.g., inches to cm)
- Stratified train-test split and standardized numeric columns

---

## 🧠 Modeling Strategy
- **Base Models**: Random Forest, Extra Trees, Decision Tree, Bagging
- **Meta-Learner**: Tuned XGBoost classifier

**Features**:
- Numerical: `DIA` (diameter), `HT` (height), `LAT`, `LON`
- One-hot encoded: Ecological Zones

**Target Variables**: PFT → Genus → Species (hierarchical)

---

## 📊 Performance Summary
| Task    | Accuracy | Weighted F1-Score |
|---------|----------|-------------------|
| **PFT**     | 90.0%    | 0.89              |
| **Genus**   | 83.3%    | 0.83              |
| **Species** | 96.9%    | 0.97              |

The models showed high consistency, especially for dominant classes (e.g., Evergreen conifer, Pinus). Site-level evaluations were conducted for PFTs.

---

## 📈 Key Visuals & Insights
All plots are included in `Images/` and `plots.ipynb`. Highlights:

- KDE maps of tree density
- Distribution plots of diameter, height, and basal area
- Correlation heatmaps
- Feature importance charts
- Scatter and box plots for structural analysis
- Pipeline architecture visualizations

---

## 📄 Project Report
Read our full methodology, evaluation strategy, modeling diagrams, and discussion in the official PDF report:

📘 [`SDSC_Report.pdf`](./SDSC_Report.pdf)

---

## ✨ Acknowledgments
This project was developed for the Fire-Ready Forests Challenge hosted by the National Data Platform and San Diego Supercomputer Center (SDSC).

Special thanks to **Pedro** and **Leticia** for their prompt and helpful responses throughout the challenge. Your support made a huge difference in helping our team resolve doubts and stay on track!

---

## 👥 Team Agni Astra
- **Guruprasad Parasnis**
- **Abhay Lal**
- **Yash Vishe**

---

## 📌 Future Work
To improve rare-class detection and generalizability, we plan to explore:

- 📉 Class-aware losses (e.g., focal loss)
- 🚐 Integration of multispectral/remote sensing & soil data
- 🌍 Spatial cross-validation techniques
- 🔀 Continual learning for incremental field data updates

---

## 💬 Contact
For questions, suggestions, or collaborations, feel free to open an issue or reach out via email.

---
