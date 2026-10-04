# Cardiovascular Risk Visualization & Prediction

### Multimodal AI Hackathon 2026

**Track A — Cardiovascular Risk Visualization & Prediction**

## 📌 About

This project is being developed for the **Multimodal AI Hackathon 2026 – Track A**.

The current implementation focuses on building the **machine learning pipeline** for predicting:

* Overall Coronary Artery Disease (CAD)
* LAD stenosis
* LCX stenosis
* RCA stenosis

---

## 📊 Dataset

We are using the **Extension of Z-Alizadeh Sani Dataset**.

* 303 patient records
* 59 original columns
* 55 features used as model inputs

The dataset contains demographic, clinical, ECG, laboratory, and echocardiographic features.

---

## 🔐 Data Preprocessing

The following target-related columns were excluded from the model inputs to prevent data leakage:

```text
Cath
LAD
LCX
RCA
```

Categorical features were converted into numerical values.

Examples:

```text
Male / Fmale → 1 / 0
Y / N → 1 / 0
BBB → 0 / 1 / 2
VHD → 0 / 1 / 2 / 3
```

---

## 🤖 Model Comparison

Four machine learning models were evaluated:

* Logistic Regression
* Random Forest
* Support Vector Machine (SVM)
* XGBoost

Models were evaluated using **5-fold Stratified Cross-Validation**.

Evaluation metrics:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC

---

## 🏆 Selected Models

Based on the model comparison:

| Target | Selected Model | Accuracy |    F1 | ROC-AUC |
| ------ | -------------- | -------: | ----: | ------: |
| CAD    | SVM            |    87.8% | 91.3% |   92.7% |
| LAD    | Random Forest  |    78.6% | 82.3% |   85.7% |
| LCX    | Random Forest  |    68.7% | 57.9% |   72.5% |
| RCA    | Random Forest  |    68.3% | 55.8% |   72.3% |

---

## 📁 Current Project Structure

```text
cardio-risk-3d/
│
├── data/
│   └── extension of Z-Alizadeh Sani Dataset.xlsx
│
├── ml/
│   ├── check_data.py
│   ├── model_comparison.py
│   └── train_final_models.py
│
├── models/
│   ├── cad_model.pkl
│   ├── lad_model.pkl
│   ├── lcx_model.pkl
│   ├── rca_model.pkl
│   └── feature_columns.pkl
│
├── backend/
├── frontend/
└── README.md
```

---

## ▶️ Run the ML Pipeline

### Check Dataset

```bash
python ml/check_data.py
```

### Compare Models

```bash
python ml/model_comparison.py
```

### Train Final Models

```bash
python ml/train_final_models.py
```

The final trained models are saved in the `models/` directory.

---

## ✅ Current Progress

* [x] Dataset loading
* [x] Dataset inspection
* [x] Data preprocessing
* [x] Target encoding
* [x] Data leakage prevention
* [x] Model comparison
* [x] 5-fold cross-validation
* [x] Model selection
* [x] Final model training
* [x] Model weights saved

---

## 🔮 Next Steps

* [ ] SHAP explainability
* [ ] FastAPI backend
* [ ] React frontend
* [ ] Interactive 3D heart
* [ ] LAD/LCX/RCA risk visualization
* [ ] Clinical dashboard
