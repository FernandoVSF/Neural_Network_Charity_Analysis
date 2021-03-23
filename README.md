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
     
    - Model Summary
    ![sum](/sum.png)
    
    - Activation Functions:
      - Elu: 3
      - Sigmoid: 1
    - Those parameters were the ones that produced the highest accuracy level
    - However, target model performance was not achieved.  Our optimazation showed 0.7285 accuracy
    - To increase model performance, we took the following steps:
      - Remove INCOME_AMT feature
      - Increase number of bins in APPLICATION_TYPE and CLASSIFICATION to 10 + others for each column
      - Increase number of neurons in second layer to 40
      - Create a third layer with 12 neurons
      - Change activation function in layers to ELU
  
## Summary

These steps only increased marginally (each of them a little bit) model performance in terms of accuracy.  However, it is taking longer to run.  To solve this classification problem, we recommend trying a Random Forest, since it is able to achieve comparable predictive accuracy on large tabular data with less code and faster performance.

- Model Performance
  ![perf](/perf.png)
