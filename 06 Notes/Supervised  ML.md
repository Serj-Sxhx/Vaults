
## What is (supervised) machine learning? Concisely put, it is the following:

-   ML systems learn how to combine input to produce useful predictions on never-before-seen data.

Let's explore fundamental machine learning terminology.

## Labels

A **label** is the thing we're predicting—the `y` variable in simple linear regression. The label could be the future price of wheat, the kind of animal shown in a picture, the meaning of an audio clip, or just about anything.

## Features

A **feature** is an input variable—the `x` variable in simple linear regression. A simple machine learning project might use a single feature, while a more sophisticated machine learning project could use millions of features, specified as:

x1,x2,...xN

In the spam detector example, the features could include the following:

-   words in the email text
-   sender's address
-   time of day the email was sent
-   email contains the phrase "one weird trick."

## Examples

An **example** is a particular instance of data, **x**. (We put **x** in boldface to indicate that it is a vector.) We break examples into two categories:

-   labeled examples
-   unlabeled examples

Use labeled examples to **train** the model. In our spam detector example, the labeled examples would be individual emails that users have explicitly marked as "spam" or "not spam."

For example, the following table shows 5 labeled examples from a [data set](https://developers.google.com/machine-learning/crash-course/california-housing-data-description) containing information about housing prices in California:

An **unlabeled example** contains features but not the label. 

Once we've trained our model with labeled examples, we use that model to predict the label on unlabeled examples. In the spam detector, unlabeled examples are new emails that humans haven't yet labeled.

## Models

A model defines the relationship between features and label. For example, a spam detection model might associate certain features strongly with "spam". Let's highlight two phases of a model's life:

-   **Training** means creating or **learning** the model. That is, you show the model labeled examples and enable the model to gradually learn the relationships between features and label.
    
-   **Inference** means applying the trained model to unlabeled examples. That is, you use the trained model to make useful predictions (`y'`). For example, during inference, you can predict `medianHouseValue` for new unlabeled examples.

## Regression vs. classification

A **regression** model predicts continuous values. For example, regression models make predictions that answer questions like the following:

-   What is the value of a house in California?
    
-   What is the probability that a user will click on this ad?
    

A **classification** model predicts discrete values. For example, classification models make predictions that answer questions like the following:

-   Is a given email message spam or not spam?
    
-   Is this an image of a dog, a cat, or a hamster?


## L2 Loss or Squared Error 
Square of the distance between prediction and label
(observation - prediction)^2

![[Screenshot 2021-06-10 at 12.56.42.png]]


## Mean square error** (**MSE**) 

: Is the average squared loss per example over the whole dataset. 

To calculate MSE, sum up all the squared losses for individual examples and then divide by the number of examples:


MSE\=1/N∑(x,y)∈D(y−prediction(x))2

where:

-   (x,y) is an example in which
    -   x is the set of features (for example, chirps/minute, age, gender) that the model uses to make predictions.
    -   y is the example's label (for example, temperature).
-   prediction(x) is a function of the weights and bias in combination with the set of features x.
-   D is a data set containing many labeled examples, which are (x,y) pairs.
-   N is the number of examples in D.

Although MSE is commonly-used in machine learning, it is neither the only practical loss function nor the best loss function for all circumstances.