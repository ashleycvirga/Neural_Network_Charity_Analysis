# Neural_Network_Charity_Analysis

Using Machine Learning and Neural Networks  with tensorFlow to assist the Alphabet Soup Foundation in predicting the best charities to invest in

## Overview 

The Alphabet Soup Foundation is trying to decide which charities to invest in out of the thousands of applications for funding they have received.  They want to see their foundation dollars invested in the charities who successfully do the most good.
This project creates a neural network model in Python using tensorFlow to predict the charities whose efforts have the most successful outcomes. Using the foundation's data set of applications, the neural network will predict the groups of charities that are marked as sucessful. This will help the organization save time in narrowing down funding applications and help ensure that their dollars are invested in charities that successfully do the most good.


## Results: 

Using bulleted lists and images to support your answers, address the following questions.
### Data Preprocessing

What variable(s) are considered the target(s) for your model?

- 'Is_Successful' is our target variable. We want the nn model to predict which charity applications come from charities that are successful.

![target](Images/target_variable.png)

What variable(s) are considered to be the features for your model?

- 'application_type', 'classification', 'use-case', 'organization', 'income-amt', special_considerations', 'ask_amount' are all factors that help the model weigh their influence on it's ability to predict the success of charity that has applied to the foundation.

![features](Images/features_list.png)

What variable(s) are neither targets nor features, and should be removed from the input data?

- 'EIN' and 'NAME'are not relevant factors to determining an applicants success and thus are neither features nor are they target variables. The EIN column was dropped and the name column was removed and then added back in as the index for the data set.

- 'status' is neither a target nor a feature as it simply describes whether the organization that has applied to the foundation is active or not. This should be used to filter out all inactive charities and drop the column in the pre-processing phase before feeding the data into the model for training.

- the challenge instructions did not include this as a step but I will drop the column in the optimization phase.

![neither](Images/neither.png)

### Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

- The input layer has the same number of nodes as the number of features in our model. In this case it is 45. (When encoding categorical variables with One Hot Encoder, the categories of each categorical variable became a new column and this a new 'feature' to the model).

- Considering that the model has 45 features as inputs, I decided to start with two hidden layers with 80 nodes in the first(about double the nodes as the number of features) and 30 nodes in the second(a median number between the # of features and the number of nodes in the first layer).

- The first and second layer use a ReLU activation function because it identifies non-linear characteristics from the input values.

- The output layer uses a sigmoid activation function because it best represents the shape of a probability function. In this case we want to determine the probability that a charity 'IS_SUCCESSFUL' and thus the sigmoid function is most appropriate here.

![OG_params](Images/OG_params.png)


## Steps to try to increase model accuracy:

### Initial Model Training Run

Accuracy: 72.5%  Loss: 55.9% over 30 epochs


![OG_Accuracy](Images/OG_Accuracy.png)

### First Optimization Attempt

- Removed 'SPECIAL_CONSIDERATIONS' column

![a1 changes](Images/attempt1_changes.png)

Accuracy:

![attempt1_accuracy](Images/attempt1_accuracy.png)

### Second Optimization Attempt

- Removed zero value rows in the 'STATUS' column and then dropped the column.

- Kept 'SPECIAL_CONSIDERATIONS' column dropped

![2 changes](Images/attempt2_changes.png)

Accuracy: 

![attempt2_accuracy](Images/attempt2_accuracy.png)


### Third Optimization Attempt

- Put 'SPECIAL_CONSIDERATIONS' column back in

- Removed zero value rows in the 'STATUS' column and then dropped the column.

- increased the number of neurons and hidden layers

![attempt3_params](Images/attempt3_params.png)

Accuracy: 

![attempt3_accuracy](Images/attempt3_accuracy.png)

Were you able to achieve the target model performance?

Unfortunately I was not able to achieve the target accuracy of 75%.


## Summary 

Overall, through optimization, the model accuracy just seemed to get worse with the changes I made.
I later realized that I need to add the name column back in but I will not be able to do that all and re-run it in time for this turn in.  I will go back and correct after turn in.

I would recommend the following model revisions for future optimization attempts:

- list model's weights for each feature in ascending order and drop columns with near zero weights

- getting a better understanding of the categorical variables and finding better ways to preprocess those data columns for the model.

- Further exploring ideal number of neurons, hidden layers and activation functions. 
