# **Forest Structure Classification for Wildfire Modeling**

## **Project Overview**
This project focuses on classifying trees using **Terrestrial Laser Scanning (TLS) data** to predict:
1. **Plant Functional Type (PFT)**
2. **Tree Genus**
3. **Tree Species**

The goal is to **improve wildfire modeling** by leveraging sensed data to supplement traditional field-collected data.

## **Project Structure**
```
📂 forest-structure-classification
├── 📜 README.md                 # Project documentation
├── 📜 requirements.txt          # Dependencies
├── 📜 report.pdf                # Detailed project report
├── 📂 data/                      # Dataset directory (not included in repo)
├── 📂 notebooks/                 # Jupyter notebooks for data exploration and modeling
│   ├── pft_classification.ipynb  # Model for Plant Functional Type
│   ├── genus_classification.ipynb # Model for Genus Classification
│   ├── species_classification.ipynb # Model for Species Classification
│   ├── evaluation.ipynb         # Model evaluation & comparison
├── 📂 models/                    # Saved trained models
└── 📂 src/                        # Scripts for data processing & model training
```

## **Setup Instructions**
### **1. Clone the Repository**
```bash
git clone https://github.com/yourusername/forest-structure-classification.git
cd forest-structure-classification
```

### **2. Install Dependencies**
Create a virtual environment (optional but recommended):
```bash
python -m venv env
source env/bin/activate  # On Windows, use `env\Scripts\activate`
```
Install required packages:
```bash
pip install -r requirements.txt
```

### **3. Download Data**
Place the required TLS and reference field data in the `data/` directory. Ensure the dataset structure matches the expectations outlined in the report.

### **4. Run Jupyter Notebooks**
Launch Jupyter Notebook to explore and execute models:
```bash
jupyter notebook
```
Open the relevant notebook under the `notebooks/` directory.

## **Modeling Approach**
### **Step 1: Data Preprocessing**
- Clean and preprocess TLS data.
- Extract relevant tree features.
- Merge field data for ground-truth labels.

### **Step 2: Classification Models**
- **PFT Classification** → Random Forest / SVM
- **Genus Classification** → Gradient Boosting / CNN
- **Species Classification** → Deep Learning (ResNet / Transformers)

### **Step 3: Model Evaluation**
- Compute accuracy, precision, recall, and F1-score.
- Compare predicted distributions to actual field data.

## **Results and Findings**
- **How well did the model perform?** (Accuracy & distribution comparison)
- **Challenges and limitations**
- **Potential improvements**

## **Next Steps**
- Enhance feature engineering (e.g., spectral data, additional attributes).
- Experiment with ensemble methods.
- Explore transfer learning for species classification.

## **Authors**
- [Your Name](https://github.com/yourusername) - UCSD CSE

## **License**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

