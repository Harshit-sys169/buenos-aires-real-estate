Buenos Aires Real Estate Price Prediction
==========================================

Comprehensive real estate analysis with progressive complexity: from linear regression to advanced regularization techniques, feature selection methods, and ensemble stacking.

Project Overview
----------------

Analyzed 5 datasets of Capital Federal (Buenos Aires) apartments to predict prices. The analysis progresses through four main phases:

**Task 1: Simple Linear Regression**
- Baseline linear regression on apartment surface area
- Understanding fundamental relationship between features and target

**Task 2: Geographic Features**
- Latitude/longitude based pricing
- 3D surface visualization of price gradients across neighborhoods
- Understanding geographic value drivers

**Task 3: Neighborhood Analysis**
- One-hot encoding for categorical neighborhood data
- Ridge regression with L2 regularization
- Understanding regularization impact on correlated features

**Task 4 (Advanced):**

*Task 4 - Regularization Comparison* (`task_4_advanced.py`)
- Linear Regression: Baseline unregularized model
- Ridge (L2): Uniform coefficient shrinkage, good for correlated features
- Lasso (L1): Drives coefficients to zero, performs automatic feature selection
- ElasticNet: Combines L1 and L2 penalties
- Analysis of how regularization strength (alpha) affects:
  * Coefficient magnitude and sparsity
  * Training vs cross-validation performance
  * Generalization ability

*Task 4 - Feature Selection* (`task_4_feature_selection.py`)
- SelectKBest: Fast univariate feature scoring
- Recursive Feature Elimination (RFE): Accounts for feature interactions
- Lasso-based: Automatic selection via L1 regularization
- Permutation Importance: Model-agnostic importance measurement
- Comprehensive comparison of when to use each method

*Task 4 - Model Stacking* (`task_4_model_stacking.py`)
- Base learners: Ridge, Random Forest, Gradient Boosting
- Stacking regressor with Ridge meta-learner
- Ensemble blending to combine complementary model strengths
- Performance comparison across all approaches

Dataset Details
----------------

**Filtering Criteria:**
- Location: Capital Federal (Buenos Aires)
- Property Type: Apartments only
- Price Range: < $400,000 USD
- Surface Area: 10th-90th percentile (removing outliers)

**Final Dataset:** ~5,000 apartments with multiple structural and geographic features

Key Competencies Demonstrated
-----------------------------

**Regularization Understanding**
- Ridge and Lasso trade-offs
- Hyperparameter tuning (alpha selection)
- Cross-validation for model evaluation
- Overfitting detection

**Feature Engineering**
- One-hot encoding for categorical variables
- Handling missing values with imputation
- Feature standardization for linear models
- Geographic feature extraction

**Feature Selection**
- Univariate scoring vs interaction-aware methods
- Sparsity vs performance trade-offs
- Model-agnostic importance measurement
- Business interpretation of selected features

**Ensemble Methods**
- Combining diverse models (linear + tree-based)
- Stacking architecture
- Meta-learner optimization
- Understanding ensemble strength through diversity

Project Structure
-----------------
```
buenos-aires-real-estate/
├── task_1.py                     # Simple linear regression
├── task_2.py                     # Geographic feature analysis
├── task_3.py                     # Neighborhood analysis with Ridge
├── task_4_advanced.py            # Regularization comparison
├── task_4_feature_selection.py   # Feature selection techniques
├── task_4_model_stacking.py      # Ensemble stacking
├── requirements.txt
└── README.md
```

How to Run
----------

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Prepare data:**
   - Place CSV files in `data/` directory matching pattern `buenos-aires-real-estate-*.csv`

3. **Run individual analyses:**
   ```bash
   python task_1.py          # Simple regression baseline
   python task_2.py          # Geographic analysis
   python task_3.py          # Neighborhood features
   python task_4_advanced.py # Regularization comparison
   ```

4. **Run feature selection analysis:**
   ```bash
   python task_4_feature_selection.py
   ```
   Generates visualizations:
   - `feature_selection_selectkbest.png`
   - `feature_selection_rfe.png`
   - `feature_selection_lasso.png`
   - `feature_selection_permutation.png`

5. **Run ensemble stacking:**
   ```bash
   python task_4_model_stacking.py
   ```
   Generates: `stacking_model_comparison.png`

Key Results
-----------

**Regularization Impact:**
- Ridge reduces overfitting while retaining all features
- Lasso automatically selects relevant features (sparsity increases with alpha)
- ElasticNet provides middle ground
- Optimal alpha chosen via cross-validation

**Feature Selection Insights:**
- SelectKBest identifies univariate relationships quickly
- RFE accounts for feature interactions
- Lasso-based selection aligns well with model performance
- Permutation importance shows real-world prediction impact

**Ensemble Performance:**
- Stacking typically outperforms individual base learners
- Combining linear and tree-based models captures complementary patterns
- Ridge meta-learner effectively weights base model predictions

Technologies Used
-----------------
- **Data Processing:** pandas, numpy
- **Machine Learning:** scikit-learn
- **Regularization:** Ridge, Lasso, ElasticNet from sklearn.linear_model
- **Feature Selection:** SelectKBest, RFE, permutation_importance
- **Visualization:** matplotlib, seaborn
- **Encoding:** category_encoders OneHotEncoder

Lessons Learned
---------------

1. **Regularization is crucial** for preventing overfitting and improving generalization
2. **Feature selection methods each tell different stories** - use multiple approaches
3. **Ensemble methods work best with diverse base learners** - combining different model families
4. **Cross-validation is essential** for honest performance estimates
5. **Hyperparameter tuning** is more important than algorithm choice for real data

---

**Author:** Harshit  
**GitHub:** https://github.com/Harshit-sys169
