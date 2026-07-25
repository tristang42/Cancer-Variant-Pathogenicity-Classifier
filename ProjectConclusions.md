**OBJECTIVES ACHIEVED**

1.  Successfully developed a series of TensorFlow-based neural network
    models to improve the prediction of pathogenicity for
    cancer-associated missense variants.

2.  Engineered biologically meaningful features, including:
    -   Amino acid physicochemical properties
    -   One-hot encoded amino acid substitutions
    -   BLOSUM62 substitution scores
    -   Mutation position features

3.  Improved the model training and evaluation pipeline through:
    -   Class weighting to mitigate class imbalance
    -   Repeated stratified K-fold cross-validation as the final evaluation strategy
    -   Repeated stratified train-test splitting across 50 independent
        iterations during earlier stages of model development
    -   ROC-based threshold optimization using Youden’s J statistic for
        split-specific classification

4.  Implemented a comprehensive evaluation framework using:
    -   Accuracy
    -   Precision
    -   Recall
    -   F1-score
    -   ROC-AUC
    -   95% confidence intervals computed across repeated model evaluations using both repeated stratified   train-test splitting (earlier models) and repeated stratified K-fold cross-validation (final model).

5.  Developed a preprocessing pipeline to clean, transform, and encode
    ClinVar variant data into machine learning-ready feature
    representations.

6.  Followed an iterative development process in which successive neural
    network architectures and biologically informed feature engineering
    strategies were introduced and evaluated. A total of nine models
    with different architectures and feature sets were developed, culminating 
    in a final model that integrated the most effective preprocessing, feature engineering, 
    neural network architecture, and evaluation methodology.

------------------------------------------------------------------------

**DATASETS**

The final dataset consisted of 2,546 missense variants across six
cancer-associated genes:

1.  TP53
2.  BRCA1
3.  BRCA2
4.  MSH2
5.  MSH6
6.  ATM

Variant Distribution by Gene

ATM: Benign 142 | Pathogenic 95

BRCA1: Benign 371 | Pathogenic 235

BRCA2: Benign 566 | Pathogenic 115

MSH2: Benign 295 | Pathogenic 153

MSH6: Benign 86 | Pathogenic 95

TP53: Benign 149 | Pathogenic 244

Overall Dataset - **Benign: 1,609** - **Pathogenic: 937**

------------------------------------------------------------------------

**Final Model Performance**

The final model integrates the most effective preprocessing methods, biologically informed feature engineering strategies, neural network architecture, and evaluation methodology developed throughout the project.

Performance was evaluated using repeated stratified K-fold cross-validation, providing a more robust and representative estimate of model generalization than earlier evaluation strategies.

| **Metric** | **Mean Performance** | **95% Confidence Interval** |
| :--------- | :------------------: | :-------------------------: |
| Accuracy | **72.3%** | 70.6% – 74.0% |
| Recall (Pathogenic) | 62.6% | 56.5% – 68.6% |
| Recall (Benign) | 77.8% | 74.0% – 81.6% |
| Precision (Pathogenic) | 65.8% | 62.5% – 69.0% |
| Precision (Benign) | 79.7% | 77.9% – 81.5% |
| F1-score (Pathogenic) | 59.6% | 54.9% – 64.3% |
| F1-score (Benign) | 77.7% | 75.7% – 79.7% |
| ROC-AUC | **0.741** | 0.713 – 0.769 |

Performance metrics are reported as the mean across repeated stratified K-fold cross-validation runs, with corresponding 95% confidence intervals.

------------------------------------------------------------------------

**Interpretation of Final Metrics**

The final model achieved an overall accuracy of **72.3%** (95% CI: **70.6%–74.0%**), demonstrating consistent predictive performance across repeated stratified K-fold cross-validation.

The model also achieved a **ROC-AUC of 0.741** (95% CI: **0.713–0.769**), indicating good discrimination between pathogenic and benign variants across a range of classification thresholds.

Performance for benign variants consistently exceeded performance for pathogenic variants:

- **Pathogenic Recall (62.6%)** indicates that the model correctly identified nearly two-thirds of pathogenic variants.

- **Benign Recall (77.8%)** indicates that over three-quarters of benign variants were correctly classified.

- **Pathogenic Precision (65.8%)** suggests that approximately two-thirds of variants predicted as pathogenic were truly pathogenic.

- **Benign Precision (79.7%)** demonstrates strong reliability when predicting benign variants.

- **Pathogenic F1-score (59.6%)** reflects the continued challenge of balancing precision and recall for the minority pathogenic class.

- **Benign F1-score (77.7%)** indicates substantially stronger performance for benign variant classification.

Overall, the model was considerably more reliable at identifying benign variants than pathogenic variants. 

------------------------------------------------------------------------

**BIOLOGICAL SIGNIFICANCE**

The results demonstrate that incorporating biological context into
machine learning models improves pathogenicity prediction compared with
relying solely on conventional sequence-based encoding.

Specifically, integrating mutation position, evolutionary substitution information (BLOSUM62), and amino acid physicochemical properties provided additional biological context that improved the model's ability to distinguish pathogenic from benign missense variants.

These findings suggest that biological feature engineering plays an
important role in pathogenic missense variant prediction and can improve
model performance even when relatively limited training data are
available.

------------------------------------------------------------------------

**MODEL LIMITATIONS**

-   The model relies on manually curated ClinVar annotations, which may
    contain conflicting or incomplete variant classifications.

-   Only six cancer-associated genes were included, limiting
    generalizability.

-   The dataset remains imbalanced, containing substantially more benign
    than pathogenic variants.

-   Only missense variants were analyzed; other mutation types (e.g.,
    nonsense, splice-site, frameshift, insertions, and deletions) were
    excluded.

-   Deep learning models generally benefit from substantially larger
    datasets to learn complex biological relationships. The relatively
    small dataset likely limited the model’s ability to identify more
    robust pathogenic patterns.

-   Performance remained consistently lower for pathogenic variants,
    likely due to class imbalance and the increased difficulty of
    distinguishing pathogenic mutations from conserved benign
    substitutions.

------------------------------------------------------------------------

**OVERALL CONCLUSION**

This project successfully demonstrated that incorporating biologically
informed feature engineering into TensorFlow-based neural networks
improves the prediction of pathogenic missense variants. 

The final model integrates progressively refined preprocessing, feature engineering,
and evaluation strategies into a reproducible machine learning pipeline for pathogenicity prediction.

------------------------------------------------------------------------

**Future Directions**

- Expand the dataset to include additional cancer-associated genes.
- Evaluate the model on larger and more comprehensive ClinVar datasets.
- Explore more advanced deep learning architectures to improve predictive performance.
- Improve class balance by incorporating additional pathogenic variants or applying advanced data balancing strategies.
- Extend the framework beyond missense variants to include other mutation types, such as insertions, deletions, splice-site, and nonsense variants.

------------------------------------------------------------------------