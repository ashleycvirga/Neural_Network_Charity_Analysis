# Neural_Network_Charity_Analysis

Using Machine Learning and Neural Networks  with tensorFlow to assist the Alphabet Soup Foundation in predicting the best charities to invest in

## Overview 

The Alphabet Soup Foundation is trying to which charities to invest in out of the thousands of applications for funding they have received.  They want to see their foundation dollars invested in the charities who successfully do the most good.
This project creates a neural network model in Python using tensorFlow to predict the charities whose efforts have the most successful outcomes. Using the foundation's data set of applications, the neural network will predict the groups of charities that are marked as sucessful. This will help the organization save time in narrowing down funding applications and help ensure that their dollars are invested in charities that successfully do the most good.


## Results: 

Using bulleted lists and images to support your answers, address the following questions.
### Data Preprocessing

What variable(s) are considered the target(s) for your model?

- 'Is_Successful' is our target variable. We want the nn model to predict which charity applications come from charities that are successful.


What variable(s) are considered to be the features for your model?

- 'application_type', 'classification', 'use-case', 'organization', 'income-amt', special_considerations', 'ask_amount' are all factors that help the model weigh their influence on it's ability to predict the success of charity that has applied to the foundation.


What variable(s) are neither targets nor features, and should be removed from the input data?

- 'EIN' and 'NAME'are not relevant factors to determining an applicants success and thus are neither features nor are they target variables. The EIN column was dropped and the name column was removed and then added back in as the index for the data set.

- 'status' is neither a target nor a feature as it simply describes whether the organization that has applied to the foundation is active or not. This should be used to filter out all inactive charities and drop the column in the pre-processing phase before feeding the data into the model for training.

- the challenge instructions did not include this as a step but I will drop the column in the optimization phase.


### Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

- The input layer has the same number of nodes as the number of features in our model. In this case it is 8.

- Considering that the model has 8 features as inputs, I decided to start with two hidden layers with # nodes in the first and # nodes in the second.

- The first and second layer use a ReLU activation function because it identifies non-linear characteristics from the input values.

- The output layer uses a sigmoid activation function because it best represents the shape of a probability function. In this case we want to determine the probability that a charity 'IS_SUCCESSFUL' and thus the sigmoid function is most appropriate here.

Were you able to achieve the target model performance?

What steps did you take to try and increase model performance?

## Summary 

Summarize the overall results of the deep learning model. 

Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.
