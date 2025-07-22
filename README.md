# MSCS 634 - Project Deliverable 2

## 📊 Regression Modeling and Performance Evaluation

### 📁 Dataset Summary
The dataset used for this project is a synthetic regression dataset consisting of:
- **1000 samples**
- **5 numerical features** (`Feature_1` to `Feature_5`)
- **1 continuous target variable** (`Target`)

This data was generated using `sklearn.datasets.make_regression`. The target variable depends linearly on the input features with added noise.

---

### ⚙️ Modeling Process
The following steps were followed:
1. **Data Preprocessing**:
   - Normalized features using `StandardScaler`
   - Verified no missing values
2. **Model Training**:
   - Implemented **Linear Regression**, **Lasso Regression**, and **Ridge Regression**
3. **Model Evaluation**:
   - Used **RMSE** and **R-squared** as evaluation metrics
4. **Residual Analysis**:
   - Plotted residuals using Seaborn to visualize model errors

---

### 📈 Evaluation Results

| Model            | RMSE     | R-squared |
|------------------|----------|-----------|
| Linear Regression | **0.105** | **0.999997** |
| Lasso Regression  | 0.237    | 0.999985  |
| Ridge Regression  | 0.133    | 0.999995  |

---

### 💡 Key Insights & Observations
- **Linear Regression** outperformed all models with the lowest RMSE and the highest R-squared score.
- **Ridge Regression** performed slightly better than **Lasso Regression**, indicating that small coefficients were useful and should not be entirely removed (as Lasso does).
- **Feature scaling** was essential to ensure all models, especially regularized ones, performed optimally.
- All models performed exceptionally well, which aligns with expectations from synthetic, well-structured data.

---

### 🚧 Challenges Encountered
- `sns.residplot(..., lowess=True)` caused an error due to missing dependency.  
  **Solution**: Installed `statsmodels` to enable `lowess` smoothing for residual plots.
- Interpreting small differences in performance was tricky due to the high overall accuracy.
  **Solution**: Focused on both residual plots and RMSE/R² metrics for deeper insight.

---

### 💾 How to Run the Project

```bash
pip install -r requirements.txt
jupyter notebook MSCS_634_ProjectDeliverable_2.ipynb
