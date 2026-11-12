# Explainable AI for Risk Stratification and Intervention Optimisation in Maternal Health

## Project overview

This project explores the application of machine learning and explainable artificial intelligence (XAI) to maternal health risk assessment, with particular attention to adolescent pregnancies and maternal health outcomes.

The research investigates whether sociodemographic and clinical characteristics can be used to identify patterns associated with maternal health risks, and whether explainability techniques can make model predictions more interpretable.

The project was developed as part of the Data Science Africa Women in Data Science and Health (DSAWH) Fellowship 2025.

## Research objectives

- Apply supervised machine learning to maternal health data.
- Compare the predictive performance of different classification algorithms.
- Examine the contribution of sociodemographic and clinical variables to model predictions.
- Use explainable AI to improve the interpretability of model outputs.
- Explore the potential relevance of data-driven risk assessment to maternal healthcare decision-making.

## Dataset and preprocessing

The analysis uses sociodemographic and clinical variables relating to maternal health. The project focuses on adolescent pregnancy and maternal outcomes.

The documented preprocessing workflow includes:

- Handling missing values.
- Encoding categorical variables.
- Addressing class imbalance.


## Machine learning methodology

Three classification algorithms were considered:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier

Model evaluation was described using accuracy, precision, recall, F1-score and confusion matrices.

The project README identifies Random Forest as the best-performing model. Numerical results and the basis for selecting the final model should be reported once verified against the notebook.

## Explainable artificial intelligence

Two complementary explainability methods were incorporated:

- **SHAP (SHapley Additive Explanations):** used to examine global feature importance and understand the variables contributing to model predictions.
- **LIME (Local Interpretable Model-Agnostic Explanations):** used to examine individual predictions and provide instance-level explanations.

The existing project summary identifies antenatal care visits, place of delivery and education level among the important predictors. These findings should be accompanied by the corresponding notebook outputs.

## Research contribution and significance

The project demonstrates an applied machine learning workflow combining predictive modelling with explainability in a maternal health context.

Its central contribution is the exploration of how predictive algorithms and interpretable outputs can be brought together to support the investigation of maternal health risk patterns. It also highlights the importance of data quality and collaboration between data scientists, healthcare professionals and policymakers when considering potential clinical applications.

The work is exploratory and should not be interpreted as a clinically validated decision-support system.

## Future directions

Further work could examine external validation, data quality, model robustness, subgroup performance and the feasibility of integrating interpretable risk-assessment approaches into maternal healthcare workflows.

## Repository contents

- `Maternal_Mortality (1).ipynb` — Jupyter Notebook containing the analysis.
- `DSAWH - Anne Project Presentation` — project presentation.
- `README.md` — project overview and methodology.

**Researcher:** Anne Amina Freitas  
**Programme:** Data Science Africa Women in Data Science and Health Fellowship, 2025
