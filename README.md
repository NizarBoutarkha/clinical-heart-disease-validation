# Clinical Heart Disease Prediction — Statistical Validation Case Study

Academic portfolio notebook analyzing the UCI Cleveland Heart Disease dataset as a clinical prediction modeling case study.

## What this project shows

This project demonstrates an end-to-end clinical data analysis workflow:

- data cleaning and missing-data handling
- exploratory statistical analysis
- correct statistical test selection
- effect-size interpretation
- logistic regression modeling
- threshold analysis for screening logic
- calibration assessment
- internal validation
- external validation across UCI hospital cohorts
- clinical interpretation and limitations

## Main notebook

Open the notebook:

[`clinical-heart-disease-project.academic.ipynb`](clinical-heart-disease-project.academic.ipynb)

## Project summary

The project uses the Cleveland Heart Disease dataset with 303 patients and converts the original multiclass target into a binary CAD outcome:

- `0` = No CAD
- `1` = CAD present

After missing-data assessment, a complete-case baseline of 297 patients is used.

The main benchmark model is a regularized logistic regression pipeline using all 13 predictors. Continuous variables are standardized and categorical variables are one-hot encoded.

## Key results

- Best logistic regression regularization: `C = 1`
- Held-out test ROC-AUC: `0.929`
- Default threshold accuracy: `0.800`
- Screening threshold selected: `0.30`
- Threshold 0.30 sensitivity: `0.929`
- Threshold 0.30 specificity: `0.812`
- Calibration Brier score: `0.111`

External validation using reduced shared predictors showed heterogeneous transfer:

- Hungarian: ROC-AUC `0.830`
- Switzerland: ROC-AUC `0.757`
- Long Beach VA: ROC-AUC `0.672`

## Clinical interpretation

The full logistic regression model with `ca` is the best benchmark model.

A second model without `ca` is more clinically realistic because `ca` is close to angiographic information.

External validation shows that performance changes across hospitals, so the model should be treated as clinical decision support, not a replacement for clinicians or diagnostic procedures.

## Why this project matters

This is not only a machine-learning exercise. It focuses on statistical validity, clinical realism, threshold tradeoffs, calibration, and transportability.

## Data source

UCI Heart Disease dataset.

The notebook loads the data from public UCI repository URLs.

## Author

Nizar Boutarkha  
Master’s student in Computational Biology / Bioinformatics / Data Analysis
