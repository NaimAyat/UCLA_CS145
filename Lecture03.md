# Lecture 3: Logistic Regression
## Supervised vs. Unsupervised Learning
* Supervised learning (classification)
  * Supervision: The training data (observations, measurements, etc.) are accompanied by labels indicating the class of the observations
  * New data is classified based on the training set
* Unsupervised learning (clustering) 
  * The class labels of training data are unknown
  * Given a set of measurements, observations, etc. with the aim of establishing the existence of classes or clusters in the data
## Prediction Problems: Classification vs. Numeric Prediction
* Classification
  * Predicts categorical class labels
  * Classifies data (constructs a model) based on the training set and the values (class labels) in a classifying attribute and uses it in classifying new data
* Numeric prediction
  * Models continuous-valued functions, i.e. predicts unknown or missing values
* Typical applications
  * Medical diagnosis: if a tumor is cancerous or benign
  * Fraud detection: if a transaction is fraudulent
  * Web page categorization
## Classification: A Two-Step Process
* For classifying future or unknown objects
1. Estimate accuracy of the model
   * The known label of the test sample is compared with the classified result from the model
   * Test set is independent of training set
   * Accuracy rate is the percentage of test set samples that are correctly classified by the model
2. If the accuracy is acceptable, use the model to classify new data
* Note: if the test set is used to select models, it is called the *validation (test) set*
## Linear Regression VS. Logistic Regression
* Linear Regression (prediction)
  * Y: continuous value
* Logistic Regression (classification)
  * Y: discrete value from m classes
