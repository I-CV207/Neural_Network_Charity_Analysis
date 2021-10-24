# Neural Network Charity Analysis

## Overview of the analysis:

The main purpose of this analysis is to apply machine learning and neural networks knowledge. With a give dataset, we are going to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

The dataset has information of over 34,000 organizations that have received funding from Alphabet Soup over the years. However some preprocessing must be done as all not all the features within the dataset are useful to build a neural network. 

## Results:

From the created model we are going to adress the following questions based on the obtained results:

### Data Preprocessing
    
    The dataset given has the following columns:
    
  - EIN and NAME—Identification columns
  - APPLICATION_TYPE—Alphabet Soup application type
  - AFFILIATION—Affiliated sector of industry
  - CLASSIFICATION—Government organization classification
  - USE_CASE—Use case for funding
  - ORGANIZATION—Organization type
  - STATUS—Active status
  - INCOME_AMT—Income classification
  - SPECIAL_CONSIDERATIONS—Special consideration for application
  - ASK_AMT—Funding amount requested
  - IS_SUCCESSFUL—Was the money used effectively
    
**What variable(s) are considered the target(s) for your model?**

The variable considered as the target is the values from the column "IS_SUCCESSFUL"

**What variable(s) are considered to be the features for your model?**

The variables that were considered as features were: "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION, "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT"

**What variable(s) are neither targets nor features, and should be removed from the input data?**

The variables that were removed as they do not provide any relevant data were the columns "EIN" and "NAME"

### Compiling, Training, and Evaluating the Model

**How many neurons, layers, and activation functions did you select for your neural network model, and why?**

For the neural network model the following attributes were chosen:

- Input layer: 80 neurons following a thumb rule for less than double than our input variables, as the activation function RELU was chosen as is idela for looking at positive non-linear data for classification.
- Hidden layer 1: 30 neurons just as the input layer following the thumb rule and RELU for the activation function.
- Output layer: Sigmoid activation function as we are looking for a binary clasiffication.

**Were you able to achieve the target model performance?**

From our model we manage to obtain an accuracy of 72.57% as seen on the image below, therefore it could be considered as a good model.

![image](https://user-images.githubusercontent.com/83261520/138578540-bf876a6e-d751-4ef2-84f0-822aa094f749.png)


**What steps did you take to try and increase model performance?**

Three attemps were done in order to try to improve the performance of the model, in summary the more important steps taken are explained for each one:

***1st attemp***

- Eliminate columns EIN and NAME.
- Reduce labels of column APLICATION TYPE from 17 to 9.
- Reduce labels of column CLASSIFICATION from 71 to 6.
- Input layer with RELU activation function and 80 neurons.
- Hidden layer with RELU activation function and 60 neurons.
- Training of 400 epochs.

From this attemp we manage to increase the accuracy of the model to 72.71% which is not that different than the first model created.

![image](https://user-images.githubusercontent.com/83261520/138578839-201b084f-d334-4911-a66d-c29599659209.png)

***2nd attemp***

- Eliminate columns EIN and NAME.
- Eliminate columns SPECIAL_CONSIDERATIONS and STATUS.
- Reduce labels of column APLICATION TYPE from 17 to 9.
- Reduce labels of column CLASSIFICATION from 71 to 6.
- Input layer with RELU activation function and 80 neurons.
- Hidden layer with RELU activation function and 60 neurons.
- Hidden layer with RELU activation function and 30 neurons.
- Training of 400 epochs.

From this attemp we manage to increase the accuracy of the model to 72.57% which is the same accuracy as first model created, even if this attemp had an additional layer.

![image](https://user-images.githubusercontent.com/83261520/138578937-30eb6065-bd92-4fd2-b7dc-151c4d25bc2d.png)

***2nd attemp***

- Eliminate columns EIN and NAME.
- Eliminate columns SPECIAL CONSIDERATIONS and STATUS.
- Reduce labels of column AFFILIATION from 6 to 3.
- Reduce labels of column USE CASE from 5 to 3.
- Reduce labels of column APLICATION TYPE from 17 to 9.
- Reduce labels of column CLASSIFICATION from 71 to 6.
- Reduce labels of column INCOME AMT from 9 to 6.
- Input layer with leaky RELU activation function and 80 neurons.
- Hidden layer with leaky RELU activation function and 60 neurons.
- Training of 100 epochs.

From this attemp we manage to increase the accuracy of the model to 72.87% by keeping the same number of layers, bining the variables and changing the activation functions of the layers.

![image](https://user-images.githubusercontent.com/83261520/138579019-1dba0763-025f-4a7f-bfc7-6f320003dc4a.png)


### Summary: 

The created model got an overal accuracy of 72%, although some attemps were made in order to improve its performance, the result were not that impressive, nevertheless this does not mean that the model is useless, with the results obtained we can imply that it is a good model.

In order to increase the performance of the model we could apply a supervised machine learning algorithm instead of a neural network as it could help us to understand the wich variables have more participation in the outcome unlike a neural network that sometimes is harder to explain the reason of the result.
