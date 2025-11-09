# ⚙️ Predicting Manufacturing Defects: Stacked Ensemble Model

This project addresses the Kaggle competition, **Predicting Manufacturing Defects**, by developing and evaluating a machine learning model to accurately identify defective items on a manufacturing line. The primary goal was to achieve high **Recall** to minimize missed defects (False Negatives), which is critical in a quality control context.

## 🌟 Project Summary

This solution employs a **Stacked Ensemble** approach, combining the strengths of two powerful algorithms: **Random Forest** and **XGBoost**.

* **Primary Algorithm (Base Layer):** Random Forest
* **Secondary Algorithm (Meta-Learner):** XGBoost

### Key Results

The model performance was optimized for the minority class (defects), yielding high metrics crucial for a manufacturing quality control system.

| Metric | Result |
| :--- | :--- |
| **Recall (Defect Class)** | **99.39%** |
| **Accuracy** | **95.47%** |
| **F1-Score** | *[Insert your F1-Score here]* |
| **ROC AUC** | *[Insert your ROC AUC here]* |

---

## 💻 Tech Stack & Dependencies

The project is built using Python and leverages standard data science libraries.

* **Python** (3.x)
* **pandas** (for data manipulation)
* **numpy** (for numerical operations)
* **scikit-learn** (for Random Forest, scaling, and metrics)
* **XGBoost** (for the meta-learner and general boosting)
* **Matplotlib/Seaborn** (for visualization)

---

## 🚀 Getting Started

### Prerequisites

You need Python installed. We recommend setting up a virtual environment.

```bash
python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate     # On Windows
