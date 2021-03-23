# Neural Network Charity Analysis
Neural Network analysis on charity applications.
  
## Overview of the analysis
Using machine learning, neural networks and the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

The following outpits will be produced:

- Preprocessing Data for a Neural Network Model
- Compile, Train, and Evaluate the Model
- Optimize the Model
- A Written Report on the Neural Network Model

## Resources
- Data Source: charity_data.csv file
- Software: Python, SKLearn, Pandas, TensorFlow, Jupyter Notebook

## Results
We tryed different combination of paraneters, including adding/removing features, adding neurons to hidden layers, adding hidden layers, changing activation function, and the best results were obtained as follows:

  - Data Preprocessing
    - Target Variable:
      - IS_SUCCESSFUL
    - Feature Variables:
      - APPLICATION_TYPE
      - AFFILIATION
      - CLASSIFICATION
      - USE_CASE
      - ORGANIZATION
      - STATUS
      - SPECIAL_CONSIDERATIONS
      - ASK_AMT
    - Variables Removed from Input Data:
      - EIN
      - NAME
      - INCOME_AMT
  
  - Compiling, Training, and Evaluating the Model
    - Neurons:
      - Layer 1: 80
      - Layer 2: 40
      - Layer 3: 12
    - Layers: 4 (Including output layer)
    - Activation Functions:
      - Elu: 3
      - Sigmoid: 1
    - Those parameters were the ones that produced the highest accuracy level
    
  - Precision:     0.99
  - Recall:        0.61

   ![naive](/naive.png)
  
### SMOTE Oversampling
  - Bal. Accuracy: 0.66
  - Precision:     0.99
  - Recall:        0.69

   ![smote](/smote.png)

### Undersampling
  - Bal. Accuracy: 0.58
  - Precision:     0.99
  - Recall:        0.58

   ![under](/under.png)
   
### Combination (Over and Under) Sampling
  - Bal. Accuracy: 0.64
  - Precision:     0.99
  - Recall:        0.57

   ![combi](/combi.png)   
   
### Balanced Random Forest Classifier
  - Bal. Accuracy: 0.79
  - Precision:     0.99
  - Recall:        0.87

   ![BRF](/BRF.png)   

### Easy Ensemble AdaBoost Classifier
  - Bal. Accuracy: 0.93
  - Precision:     0.99
  - Recall:        0.94

   ![EEC](/EEC.png)   
  
## Summary

Please find below a summary table of all analysis:

Model | Bal Accy | Precision | Recall
--- | --- | --- | --
NRO | 0.65 | 0.99 |0.61
SMOTE | 0.66 | 0.99 | 0,69
Undersampling | 0.58 | 0.99 | 0.58
Combination | 0.64 | 0.99 | 0.57
BRF | 0.79 | 0.99 | 0.87
EEC | 0.93 | 0.99 | 0.94

Looking at the results, we can conclude that we have high precision scores for all models, since given data assymetry, not many low risk are predicted as high risk.  However we can see a lot of difference in the models through the recall score, which shows the ability of finding all positive high risk samples.

Therefore, we recommend using Easy Ensemble AdaBoost Classifier, since it ensemblse AdaBoost learners trained on different balanced boostrap samples, increasing the ability of finding positive high risk samples, providing the highest ballanced accuracy score.

In the other hand we don't recommed for this exercise the use of undersampling, since it involves loss of data from the majority class, decreasing even more the recall rate, and therefore, the ballanced accuracy score.
