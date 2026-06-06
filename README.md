# Cross-Validation vs Hold-Out Testing
## An Empirical Comparison of Model Evaluation Methods

Reliable model evaluation is essential in machine learning. Two of the most widely used evaluation approaches are hold-out testing and k-fold cross-validation. While both methods aim to estimate how well a model will perform on unseen data, they differ in their susceptibility to sampling variation and computational cost. This project investigates the impact of evaluation methodology on model performance estimates and ranking stability using the Diabetes Health Indicators dataset. The study compares cross-validation and hold-out testing across multiple classification algorithms and examines how dataset size influences the reliability of model evaluation.

**OBJECTIVES -**

The primary objectives of this project are:
- Compare cross-validation and hold-out testing as model evaluation strategies.
- Evaluate the performance of several classification algorithms.
- Investigate the stability of model rankings under different evaluation methods.
- Examine how reducing dataset size affects evaluation reliability.
- Assess the relative merits of cross-validation and hold-out testing in practical machine learning workflows.

**DATASET -** 

The experiments were conducted using the Diabetes Health Indicators dataset derived from the CDC Diabetes Health Indicators data collection. The dataset contains approximately 70,000 observations and a range of health-related features used to predict diabetes outcomes. To investigate the effect of dataset size on evaluation stability, experiments were performed on:
- The full dataset (~70,000 observations)
- A random sample of 3,000 observations

**MODELS EVALUATED -** 

The following classification algorithms were evaluated:
- k-Nearest Neighbours (default parameters)
- k-Nearest Neighbours (k = 100)
- Decision Tree (default parameters)
- Decision Tree (max_depth = 10)
- Gaussian Naive Bayes

Feature scaling was applied prior to training the k-Nearest Neighbour models.

**EVALUATION METHODOLOGY -** 

Two evaluation strategies were compared:

1. Cross-Validation - Models were evaluated using k-fold cross-validation, where the dataset was divided into multiple folds and each fold was used as a test set once. Final performance was calculated as the average across all folds.

Advantages:
- Reduces the effect of random train-test splits
- Produces more stable performance estimates
- Makes better use of available data

2. Hold-Out Testing - Models were evaluated using a single 2:1 train-test split.

Advantages:
- Simple to implement
- Computationally efficient
- Suitable for large datasets

Disadvantages:
- More sensitive to the choice of train-test split
- Can produce less stable performance estimates

**KEY FINDINGS -** 

Full Dataset (~70,000 Observations)
- Cross-validation and hold-out testing produced nearly identical accuracy estimates.
- Model rankings remained unchanged across both evaluation methods.
- The large dataset size resulted in highly stable performance estimates.

Reduced Dataset (3,000 Observations)
- Overall model performance decreased slightly.
- Greater variation emerged among lower-ranked models.
- Cross-validation produced more consistent performance estimates.
- Hold-out testing became more sensitive to sampling variation.

**OVERALL CONCLUSION -** 

The experiments demonstrate that hold-out testing can provide reliable results when large amounts of data are available. However, as dataset size decreases, cross-validation becomes increasingly valuable due to its ability to reduce the impact of random sampling variation and provide more stable model comparisons.


**LIMITATIONS -** 

Several limitations should be considered when interpreting the results:
- Only a small set of classification algorithms and hyperparameter configurations were evaluated.
- Classification accuracy was used as the primary evaluation metric; alternative metrics may provide additional insights.
- Hold-out testing was performed using a single train-test split, meaning results may vary slightly under different random partitions.
- The conclusions are based on a single dataset and may not generalise to all machine learning problems.

Despite these limitations, the experiments provide a useful comparison of evaluation methodologies under both large and small sample conditions.

**FUTURE WORK -**

Potential extensions of this study include:
- Performing repeated hold-out testing across multiple random train-test splits.
- Evaluating additional classification algorithms such as Random Forests, Support Vector Machines, and Gradient Boosting methods.
- Investigating alternative cross-validation strategies, including stratified and repeated k-fold cross-validation.
- Applying statistical significance testing to compare model performance.
- Extending the analysis to additional datasets with different characteristics and class distributions.

