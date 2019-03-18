# Lecture 6: Vector Data: Neural Network
## How A Multi-Layer Neural Network Works
* The inputs to the network correspond to the attributes measured for each training tuple 
* Inputs are fed simultaneously into the units making up the input layer
* They are then weighted and fed simultaneously to a hidden layer
  * The number of hidden layers is arbitrary
* The weighted outputs of the last hidden layer are input to units making up the output layer, which emits the network's prediction
* The network is feed-forward: None of the weights cycles back to an input unit or to an output unit of a previous layer
* From a math point of view, networks perform nonlinear regression: Given enough hidden units and enough training samples, they can closely approximate any continuous function
## Defining a Network Topology
* Decide the network topology: Specify # of units in the input layer, # of hidden layers (if > 1), # of units in each hidden layer, and # of
units in the output layer
* Normalize the input values for each attribute measured in the training tuples
* Output, if for classification and more than two classes, one output unit per class is used
* Once a network has been trained and its accuracy is unacceptable, repeat the training process with a different network topology or a different set of initial weights
## Learning by Backpropagation
* Backpropagation: A neural network learning algorithm 
* Started by psychologists and neurobiologists to develop and test computational analogues of neurons
* During the learning phase, the network learns by adjusting the weights so as to be able to predict the correct class label of the input tuples
* Also referred to as connectionist learning due to the connections between units
## Backpropagation
* Iteratively process a set of training tuples & compare the network's prediction with the actual known target value
* For each training tuple, the weights are modified to minimize the loss function between the network's prediction and the actual target value, say mean squared error
  * Stochastic gradient descent + chain rule
* Modifications are made in the “backwards” direction: from the output layer, through each hidden layer down to the first hidden layer, hence “backpropagation”
## Efficiency and Interpretability
* Efficiency of backpropagation: Each iteration through the training set takes O(|D| * w), with |D| tuples and w weights, but # of iterations can be exponential to n, the number of inputs, in worst case
* For easier comprehension: Rule extraction by network pruning
  * Simplify the network structure by removing weighted links that have the least effect on the trained network
  * Then perform link, unit, or activation value clustering
  * The set of input and activation values are studied to derive rules describing the relationship between the input and hidden unit layers
## Neural Network as a Classifier
* Weaknesses
  * Long training time
  * Require a number of parameters typically best determined empirically, e.g., the network topology or “structure.”
  * Poor interpretability: Difficult to interpret the symbolic meaning behind the learned weights and of “hidden units” in the network
* Strengths
  * High tolerance to noisy data
  * Successful on an array of real-world data, e.g., hand-written letters
  * Algorithms are inherently parallel
  * Techniques have recently been developed for the extraction of rules from trained neural networks
  * Deep neural network is powerful
