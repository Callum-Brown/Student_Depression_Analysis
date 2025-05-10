# Student Mental Health Analysis & Depression Prediction

## Project Overview
This machine learning project analyzes factors contributing to depression among students, exploring the relationships between academic pressures, lifestyle factors, and mental health outcomes. By identifying key predictors of depression, this model aims to help educational institutions develop targeted mental health interventions.

## Dataset Description
The dataset contains various features related to student demographics, academic performance, lifestyle habits, and mental health indicators. Key variables include:

- Demographic information (age, gender)
- Academic factors (CGPA, academic pressure, study satisfaction, work/study hours)
- Lifestyle indicators (sleep duration, dietary habits)
- Mental health metrics (financial stress, suicidal thoughts, family history of mental illness, depression)

## Data Exploration

### Correlation Analysis
I began by examining the relationships between variables through correlation analysis. The correlation matrix revealed several significant patterns:

![Correlation Matrix](https://github.com/yourusername/project-name/blob/main/images/correlation_matrix.png)

**Key Correlations:**
- Strong positive correlation (0.77) between work pressure and job satisfaction
- Moderate positive correlation (0.55) between suicidal thoughts and depression
- Moderate positive correlation (0.47) between academic pressure and depression
- Moderate positive correlation (0.36) between financial stress and depression
- Negative correlation (-0.23) between age and depression
- Negative correlation (-0.21) between dietary habits and depression
- Negative correlation (-0.17) between study satisfaction and depression

### Covariance Analysis
To further understand the variance and relationship between variables, I generated a covariance matrix:

![Covariance Matrix](https://github.com/yourusername/project-name/blob/main/images/covariance_matrix.png)

The covariance matrix highlights the absolute scale of relationships between variables, with notable high-variance relationships between:
- ID and several other variables (likely a statistical artifact)
- Age and depression (-0.55)
- Financial stress and depression (0.26)
- Work/study hours and depression (0.38)

## Feature Engineering & Selection
Based on initial exploratory data analysis, I identified the most important predictive features using feature importance scores from a trained model:

![Feature Importance](https://github.com/yourusername/project-name/blob/main/images/feature_importance.png)

**Top Predictors of Depression:**
1. Age (F-score: 290.0)
2. Academic Pressure (F-score: 277.0)
3. CGPA (F-score: 253.0)
4. Financial Stress (F-score: 242.0)
5. ID (F-score: 237.0)*

*Note: While ID showed high importance, this is likely a statistical artifact rather than a meaningful predictor and would be excluded from final models.

## Model Development

### Preprocessing Steps
1. **Data Cleaning**
   - Handled missing values
   - Removed outliers
   - Standardized numeric features

2. **Feature Engineering**
   - Created composite stress indicators
   - Encoded categorical variables
   - Normalized numerical values

### Model Training
I experimented with several machine learning algorithms to predict depression levels:

1. **Random Forest**
   - Performed well at capturing non-linear relationships
   - Hyperparameters optimized via grid search

2. **Gradient Boosting**
   - Showed the best overall performance
   - Effective at handling the class imbalance in depression labels

3. **Logistic Regression**
   - Served as a baseline model
   - Provided interpretable coefficients for feature importance validation

### Evaluation Metrics
The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

## Key Findings
1. **Academic factors** have a significant impact on depression, with academic pressure showing a strong positive correlation (0.47) with depression.

2. **Age** is inversely correlated with depression (-0.23), suggesting younger students may be more vulnerable to depression.

3. **Mental health indicators** are interrelated, with suicidal thoughts strongly associated with depression (0.55).

4. **Lifestyle factors** like dietary habits and sleep duration have moderate but meaningful correlations with depression, highlighting potential intervention points.

5. **Financial stress** is an important contributor to depression (0.36), suggesting financial support programs could benefit mental health.

6. The strong correlation (0.77) between **work pressure and job satisfaction** indicates these factors may need to be addressed together in interventions.

## Applications & Implications
This model can be used by:
- University counseling centers to identify at-risk students
- Educational policymakers to develop targeted mental health initiatives
- Academic advisors to understand how coursework pressure impacts mental health
- Student wellness programs to design effective interventions

## Limitations and Future Work
1. **Self-reported data**: The analysis relies on self-reported measures which may include bias.

2. **Cross-sectional design**: The data represents a single point in time; longitudinal data would better track the development of depression.

3. **Causality vs. correlation**: While correlations are identified, causal relationships require further investigation.

4. **Future enhancements**:
   - Incorporate temporal data to track mental health changes over an academic year
   - Include additional environmental and social support variables
   - Develop an early warning system for mental health concerns

## Technologies Used
- Python
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Project Structure
```
project-name/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   └── 03_modeling.ipynb
├── src/
│   ├── data_processing/
│   ├── feature_engineering/
│   └── modeling/
├── visualizations/
│   ├── correlation_matrix.png
│   ├── covariance_matrix.png
│   └── feature_importance.png
├── requirements.txt
└── README.md
```

## How to Use This Repository
1. Clone the repository
   ```
   git clone https://github.com/yourusername/project-name.git
   ```
2. Install required dependencies
   ```
   pip install -r requirements.txt
   ```
3. Run the Jupyter notebooks in the `notebooks/` directory to reproduce the analysis

## License
[Insert your chosen license here]

## Acknowledgements
[Include any acknowledgements, data sources, or inspirations]