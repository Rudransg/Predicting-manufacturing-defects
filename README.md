# ⚙️ Predicting Manufacturing Defects: Stacked Ensemble Model

This project tackles the **Predicting Manufacturing Defects** classification problem from a Kaggle dataset. The primary goal was to build a robust model to accurately identify defective items, prioritizing **Recall** to minimize missed defects (False Negatives), which is critical for quality control in manufacturing.

## 🏆 Results Summary

A **Stacked Ensemble** architecture was implemented, leveraging the strengths of two powerful tree-based algorithms. The model achieved the following performance metrics on the test set:

| Metric | Result |
| :--- | :--- |
| **Recall** | **99.39%** |
| **Accuracy** | **95.47%** |
| **Precision** | 95.42% |
| **F1-Score** | 97.36% |
| **ROC AUC** | 0.8710 |

The exceptionally high **Recall** indicates the model is highly effective at identifying nearly all actual defective units, making it suitable for a sensitive quality control application.

---

## 🧠 Model Architecture: Stacking

The final model uses a stacking approach, which combines the predictions of multiple base models to improve overall performance.

1.  **Level 0 (Base Learners):**
    * **Random Forest Classifier**
    * **XGBoost Classifier**
    * *These models were trained on the scaled raw features ($\text{X\_train\_scaled}$).*

2.  **Level 1 (Meta-Learner):**
    * **Random Forest Classifier**
    * *The final $\text{XGBoost}$ model's probability predictions ($\text{predict\_proba}$) and the $\text{Random Forest}$'s $\text{predict\_proba}$ were used as the input features for this meta-learner.*

The combination allows the meta-model to learn the optimal way to integrate the diverse predictions from the base models, resulting in the final robust prediction.

---

## 🛠️ Project Structure & Setup

### Prerequisites

* Python 3.x
* `pip` (Python package installer)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [Your Repository URL]
    cd predicting-manufacturing-defects
    ```

2.  **Install dependencies:**
    The project relies on standard data science libraries.
    ```bash
    pip install pandas numpy scikit-learn xgboost matplotlib seaborn
    ```
    *(Note: The environment also requires `kagglehub` for the data loading script included in the notebook.)*

### Data

The dataset used is **Predicting Manufacturing Defects Dataset** from Kaggle. The included Jupyter Notebook (`CLASS_PROJECT.ipynb`) contains a utility function to automatically download the data using the `kagglehub` library, provided you have configured your Kaggle API credentials.

### Running the Project

All steps—from data loading and preprocessing (scaling, PCA) to model training and evaluation—are contained in the main Jupyter Notebook:

```bash
jupyter notebook CLASS_PROJECT.ipynb
