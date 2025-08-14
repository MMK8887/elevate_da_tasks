# Breast Cancer Classification with SVM  

## 📌 Project Overview  
This project applies **Support Vector Machine (SVM)** models with **Linear** and **RBF kernels** to classify breast cancer data. The workflow includes data loading, model training, visualization of decision boundaries, hyperparameter tuning, and evaluation.  

---

## 📂 Dataset  
- **Dataset:** Breast Cancer Wisconsin dataset (`sklearn.datasets`)  
- **Features for Visualization:**  
  - `mean radius`  
  - `mean texture`  
- **Target:** Binary classification — malignant vs benign  

---

## 🔍 Data Analysis Key Findings  
1. The breast cancer dataset was successfully loaded and split into **training (70%)** and **testing (30%)** sets.  
2. Both **Linear SVM** and **RBF kernel SVM** models were successfully trained on the training data.  
3. Visualization of decision boundaries:  
   - **Linear SVM:** Clear, straight-line decision boundary.  
   - **RBF SVM:** Flexible, non-linear decision boundary.  
4. Hyperparameter tuning for **RBF SVM** using `GridSearchCV` with parameters `'C'` and `'gamma'` (5-fold cross-validation) identified the **best hyperparameters** as:  
   ```
   {'C': 1, 'gamma': 0.001}
   ```  
5. Evaluation of the tuned **RBF SVM** with 5-fold cross-validation gave a **mean accuracy** of **~0.9119 (91.2%)**.  
6. The tuned **RBF kernel SVM** shows promising performance on the dataset.  

---

## 🛠️ Technologies Used  
- **Python**  
- `scikit-learn` — model training, GridSearchCV  
- `numpy`, `pandas` — data handling  
- `matplotlib` — visualization  

---

## 📈 Results Summary  
| Model               | Kernel | C  | γ       | Mean CV Accuracy |
|---------------------|--------|----|--------|------------------|
| Linear SVM          | linear | 1  | -      | -                |
| RBF SVM (tuned)     | rbf    | 1  | 0.001  | 91.19%           |

---


