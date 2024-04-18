# CustomSGD.ipynb README

# Table of Contents
1. Overview
2. Stochastic Gradient Descent(SGD)
3. SGDClassifier
4. Implementation

# Overview
This document explains the Stochastic Gradient Descent(SGD) algorithm and how it's classifier works and is implemented, serving as a supplimentary document for the user intending to run Custom_SGD.ipynb. The implementation is done in various steps which are explained in detail. 

In short, SGD is an iterative algorithm commonly used for training large machine learning models. It initiates and updates various parameters (also called weights) with individual samples of data drawn from a bigger pile of the data while aiming convergence. The update of these parameters continue until a certain cutoff condition is obtained. Using this concept, the SGD classifier is primarily used for linear classification tasks using loss functions typically, logloss and regularization. 

This document will define and demonstrate the workings and implementation of the SGD Classifier algorithm at a very basic level. We will only implement logloss for implementing linear classification with L2 regularization for  simplicity and demonstrate how the algorithms can be custom writen. Sections 2. Stochastic Gradient Descent(SGD) and SGDClassifier will define the appropriate terms required while section 4. provides the implementation. 

# Stochastic Gradient Descent (SGD)
As the name suggests, stochastic (means involving a random variable) is a process of involving random variables(or parameters) and update the model parameters based on individual small samples. The proess involves various steps 


Sure, let's delve into more detail on how Stochastic Gradient Descent (SGD) works:

1. Initialization: Initialize the model parameters(weights and biases) at random or using some pre-defined values. In this project, we initialize and keep it to zeros. 
2. Iterative Optimization: Iterate over the training dataset multiple times (epochs), updating the model parameters after processing each data point or mini-batch. The order in which data points are processed can be randomized in each epoch.
Epochs: SGD iterates over the entire training dataset multiple times. Each complete pass over the dataset is called an epoch.
Stochastic Nature: At each iteration (or epoch), SGD randomly shuffles the training dataset. This randomness helps prevent the algorithm from getting stuck in local minima and ensures better exploration of the parameter space.
3. Gradient Calculation:
Single Sample or Mini-Batch: For each iteration, SGD updates the parameters using the gradient of the loss function with respect to a single training sample or a small subset (mini-batch) of the training data.
Gradient Approximation: Since computing the gradient of the entire training dataset can be computationally expensive, SGD approximates the true gradient using only a subset of data. This approximation introduces some noise into the gradient estimation but makes the optimization process computationally efficient.
4. Parameter Update:
Learning Rate: SGD scales the gradient by a factor known as the learning rate (η) before updating the parameters. The learning rate determines the size of the step taken in the parameter space. A large learning rate can cause the algorithm to overshoot the minimum, while a small learning rate can slow down convergence.
Update Rule: SGD updates the parameters in the opposite direction of the gradient to minimize the loss function. The general update rule is:

    θ<sub>t+1</sub> = θ<sub>t</sub>−η∇<sub>J</sub>(θ<sub>t</sub>)
    
    Where:
        1. θ<sub>t</sub> is the current parameter vector. 
        2. η is the learning rate.
        3. ∇<sub>J</sub>(θ<sub>t</sub>) is the gradient of the loss function with respect to θ<sub>t</sub>

5. Convergence:
Stopping Criteria: SGD continues iterating until a certain stopping criterion is met. Common stopping criteria include reaching a maximum number of iterations (epochs), achieving satisfactory performance on a validation set, or when the change in the loss function becomes negligible. In this project we acheive this by tracking the number of epochs. 

6. Regularization:
Regularization: To prevent overfitting, SGD incorporates regularization techniques such as L1 regularization (Lasso) or L2 regularization (Ridge). These techniques add a penalty term to the loss function, encouraging the model to learn simpler patterns and reduce overfitting. In this project, we have considered only L2 regularization. 
7. Loss Function:
Choice of Loss Function: The choice of loss function depends on the task at hand. Common loss functions for classification tasks include the hinge loss (for linear SVM), log loss (for logistic regression), and cross-entropy loss (for multi-class classification). We have considered logloss for our task. 

By repeating these steps iteratively, SGD gradually optimizes the parameters of the model, making it suitable for training large-scale machine learning models, especially when the entire dataset cannot fit into memory. Its stochastic nature allows it to escape local minima and explore the parameter space more effectively.

# SGDClassifier
As it seems from the above section, the SGDClassifier with logloss is a classification tasks. 

1. Objective: The goal of the classifier is to learn a decision boundary surface that efficiently seperates the data inot two classes by minimizing the log loss defined. The log loss will discussed later. 
2. Model: The SGD Classifier with log loss is based on logistic regression where the classifier predicts the probability of sample belonging to the given class using logistic function. 

    J(&theta;) = -1/N &sum;<sub>i=1</sub><sup>N</sup> [ y<sub>i</sub> log(&hat;p<sub>i</sub>) + (1 - y<sub>i</sub>) log(1 - &hat;p<sub>i</sub>) ]
3. Optimization:
    1. The SGDClassifieroptimizes the model parameters(weights) using stochastic gradient descent(SGD). 
    2. At each iteration (or epoch), it randomly selects a sample from the training dataset and updates the parameters to minimize the log loss. 

4. Regularization:
    1. The L2 regularization is applied to prevent overfititng by adding a penalty. 

By iteratively updating the parameters using SGD and minimizing the log loss function, the SGDClassifier with log loss learns a decision boundary that separates the data into the desired classes, making it suitable for binary classification tasks.

# Implementation
We implemented the following steps:
<br>
1. Initialize the weight_vector and intercept term to zeros

2. Create a loss function 

 $log loss = -1*\frac{1}{n}\Sigma_{for each Yt,Y_{pred}}(Ytlog10(Y_{pred})+(1-Yt)log10(1-Y_{pred}))$
- for each epoch:

    - for each batch of data points in train: (keep batch size=1)

        - Calculate the gradient of loss function w.r.t each weight in weight vector

            $dw^{(t)} = x_n(y_n − σ((w^{(t)})^{T} x_n+b^{t}))- \frac{λ}{N}w^{(t)})$ <br>

        - Calculate the gradient of the intercept

           $ db^{(t)} = y_n- σ((w^{(t)})^{T} x_n+b^{t}))$

        - Update weights and intercept 

            $b^{(t+1)}←b^{(t)}+α(db^{(t)}) $
    - Calculate the log loss for train and test with the updated weights (you can check the python assignment 10th question)
    - Append this loss in the list ( this will be used to see how loss is changing for each epoch after the training is over)

3. Compare implementation and SGDClassifier's the weights and intercept, make sure they are as close as possible i.e difference should be in order of 10^-2
