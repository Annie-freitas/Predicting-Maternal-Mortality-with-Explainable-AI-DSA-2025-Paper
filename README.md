# Explainable AI for Risk Stratification and Intervention Optimisation in Maternal Health

**A Focus on Adolescent Pregnancies and Intrapartum Complications**

**Researcher:** Anne Amina Freitas  
**Programme:** Data Science Africa Women in Data Science and Health (DSAWH) Fellowship, 2025

## 1. Project Overview

Maternal health complications remain an important public health challenge, particularly in settings where access to timely antenatal care, skilled birth attendance and emergency obstetric services may be limited. Data-driven approaches offer opportunities to investigate patterns associated with maternal complications and explore how machine learning could contribute to maternal health risk assessment.

This project explores the application of supervised machine learning and explainable artificial intelligence (XAI) to maternal health data, with particular attention to adolescent pregnancies and recorded maternal complications.

The study develops a comparative classification workflow using sociodemographic and maternal healthcare variables. It combines predictive modelling with explainability techniques to examine the factors contributing to model predictions and explores how interpretable outputs could inform maternal healthcare intervention planning.

The project was developed as part of the **Data Science Africa Women in Data Science and Health Fellowship 2025**.

## 2. Research Objectives

The project aimed to:

- Apply supervised machine learning techniques to maternal health data.
- Compare the performance of different classification algorithms in identifying records associated with maternal complications.
- Investigate the contribution of sociodemographic and maternal healthcare variables to model predictions.
- Apply explainable AI techniques to improve the interpretability of model outputs.
- Explore how model explanations could inform potential maternal health intervention strategies, particularly for adolescent pregnancies.

## 3. Dataset and Data Preparation

The analysis used a maternal health dataset containing **222 records and 21 original columns**. The dataset included an organisation-unit identifier and numerical variables relating to maternal healthcare activity, adolescent pregnancies, delivery outcomes and recorded maternal complications.

The accompanying fellowship presentation describes the dataset as comprising 222 maternal health cases from Kenyan health facilities. However, the original dataset source, collection period and geographical coverage are not independently documented in the notebook.

### Target variable construction

A binary outcome variable, `Complication`, was constructed from six recorded maternal complications:

- Antepartum haemorrhage
- Eclampsia
- Obstructed labour
- Postpartum haemorrhage
- Ruptured uterus
- Sepsis

A record was classified as having a complication (`1`) if at least one of these conditions was recorded; otherwise, it was classified as having no recorded complication (`0`).

### Input variables

Eleven numerical variables were selected as model inputs, covering:

- Assisted vaginal deliveries
- Breech deliveries
- Caesarean sections
- Live births
- Adolescent pregnancies aged 10–14 at first antenatal care visit
- Adolescent pregnancies aged 15–19 at first antenatal care visit
- Normal deliveries
- Four antenatal care visits
- Women receiving uterotonics during the third stage of labour
- Carbatosin administration within one minute
- Oxytocin administration within one minute

### Data preparation

The notebook's initial data-quality assessment identified no missing values and no exact duplicate rows in the original dataset. Column names were standardised before analysis.

The data were divided into training and testing subsets using an 80:20 split, with `random_state=42`. Feature scaling was performed using `StandardScaler`, fitted on the training data and applied to the test data.

The notebook does not demonstrate a SMOTE or other resampling procedure; therefore, class balancing is not reported as a completed preprocessing step here.

## 4. Machine Learning Methodology

Three supervised classification algorithms were implemented and compared:

1. **Random Forest Classifier:** an ensemble learning method combining multiple decision trees to generate classification predictions.
2. **Decision Tree Classifier:** a tree-based algorithm that produces predictions through sequential feature-based decision rules.
3. **Logistic Regression:** a statistical classification approach used as a comparative baseline.

Model performance was assessed using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices

### Model performance

The notebook reported the following test-set results:

| Metric | Random Forest | Decision Tree | Logistic Regression |
|---|---:|---:|---:|
| Accuracy | 1.00 | 0.98 | 0.96 |
| Weighted precision | 1.00 | 0.98 | 0.91 |
| Weighted recall | 1.00 | 0.98 | 0.96 |
| Weighted F1-score | 1.00 | 0.97 | 0.93 |

Random Forest achieved the highest reported performance across the evaluated metrics and was identified as the best-performing model in this comparison.

However, the test set contained only 45 records, including 43 records classified as having complications and two without complications. This substantial class imbalance limits the interpretation of the reported performance, particularly the model's ability to distinguish records without complications.

The results should therefore be interpreted as exploratory findings rather than evidence of established predictive reliability.

## 5. Explainable Artificial Intelligence

To examine the interpretability of the classification models, two explainability techniques were implemented: SHAP and LIME.

### SHAP: Global feature interpretation

SHAP (SHapley Additive Explanations) was implemented using `TreeExplainer` for the Random Forest and Decision Tree models.

The analysis generated global feature-importance visualisations to examine the contribution of input variables to model predictions. This provided a way to investigate how maternal healthcare and sociodemographic variables influenced the classification outputs.

### LIME: Local prediction explanations

LIME (Local Interpretable Model-Agnostic Explanations) was implemented to investigate individual model predictions.

The approach generated instance-level explanations for selected test observations, providing a complementary perspective to the global feature-importance analysis.

Together, SHAP and LIME provided global and local approaches to interpreting the behaviour of the tree-based classification models.

## 6. Intervention Guidance Framework

In addition to predictive modelling and explainability, the project incorporated a separate rule-based function to generate potential maternal healthcare recommendations from recorded indicators.

The implemented rules considered:

- **Antenatal care:** recommending increased antenatal care attendance where the recorded number of visits was below four.
- **Adolescent maternal support:** identifying records with adolescent pregnancy indicators for additional consideration and support.
- **Uterotonic administration:** identifying records where the recorded oxytocin administration indicator was below the specified threshold.

The fellowship presentation also proposed risk-based recommendations, including referral for critical-risk cases, additional antenatal care and adolescent-specific support.

These recommendations represent exploratory guidance based on predefined rules. They were not established through a clinically validated intervention optimisation algorithm or evaluated in a prospective healthcare setting.

## 7. Research Contribution and Significance

The project demonstrates an applied data science workflow that brings together:

- Maternal health data preparation and exploratory analysis.
- Binary outcome construction from recorded maternal complications.
- Comparative supervised machine learning.
- Model evaluation using multiple classification metrics.
- Global explainability through SHAP.
- Local explainability through LIME.
- Rule-based intervention guidance.

Its contribution lies in exploring how predictive modelling and interpretable machine learning can be applied together to investigate patterns associated with maternal complications, while considering the potential relevance of these findings to maternal healthcare planning.

The project also highlights the importance of explainability when applying AI techniques to health-related problems, where understanding model behaviour is important alongside predictive performance.

## 8. Limitations and Future Directions

The study has several limitations that should be considered when interpreting its findings.

**Dataset size and representativeness:** The analysis uses 222 records, which limits the generalisability of the findings. The original dataset source and collection period also require further documentation.

**Class imbalance:** The test set contained only two records without complications, making performance estimates for this class particularly uncertain.

**Validation:** The notebook uses a single train-test split. Further work should include cross-validation, repeated evaluation and external validation using independent datasets.

**Prediction timing and potential data leakage:** Some input variables relate to delivery and maternal healthcare interventions, while the target is constructed from recorded complications. Further investigation is needed to establish whether all predictors would be available before the outcome occurs and whether the model is suitable for prospective risk assessment.

**Clinical validation:** The model and rule-based recommendations have not been clinically validated or evaluated in real-world maternal healthcare workflows.

Future research could address these limitations through larger and more representative datasets, improved validation strategies, subgroup performance assessment, temporal analysis and collaboration with maternal healthcare professionals.

## 9. Repository Contents

| File | Description |
|---|---|
| `Maternal_Mortality (1).ipynb` | Jupyter Notebook containing data preparation, classification modelling, model evaluation and explainability analysis. |
| `DSAWH - Anne Project Presentation.pptx` | Fellowship project presentation outlining the research motivation, proposed framework, findings and recommendations. |
| `README.md` | Project overview, research objectives, methodology, findings and limitations. |

## 10. Conclusion

This project explores the application of explainable machine learning to maternal health data, with particular attention to adolescent pregnancies and recorded maternal complications.

By combining comparative classification algorithms with SHAP and LIME, the work investigates both predictive performance and the interpretability of model outputs. The additional rule-based recommendation component explores how analytical findings could be translated into potential maternal healthcare guidance.

Although further validation and methodological development are required before any clinical application, the project demonstrates the practical use of data science and explainable AI in investigating a significant public health challenge.

---

**Researcher:** Anne Amina Freitas  
**Programme:** Data Science Africa Women in Data Science and Health Fellowship, 2025  
**Project area:** Applied Machine Learning | Explainable AI | Maternal Health | Health Data Science
