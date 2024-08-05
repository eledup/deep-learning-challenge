# Alphabet Soup Charity Funding Prediction Model
## Overview
A charity organisation wants to develop a tool which helps to select which funding applications are most likely to be successful

## Data Preprocessing
### Data
The organisation have collected a set of data containg over 34,000 applications for funding. This data includes information about:
    - ID columns (ein and name)
    - application type
    - industry sector affiliation
    - organisation classification
    - use case for funding
    - status
    - income amount
    - special considerations
    - funding amount requested
    - was it successful/was the money used well?

### Removeable variables
The id columns could be removed from the data since they do not add any information from which the model might be able to learn.

The categories of application type and organisation classification can both be adapted. Using value counts, the rarest occurances in these columns can be replaced with a stand in field of 'other'. This should help a model to not be confused by rare values.

## Compiling, Training, and Evaluating the Model

### Model Set Up
The model started with two layers, both with 30 neurons, and both using the relu activation function. The output layer had a sigmoid function.
This felt a safe starting point to see how the model ran, without using too much computing power.

With set up the model produced: a loss of 0.5508, andd an accuracy of 0.7282.

### Model Performance
After this the model was optimised, ideally it would have achieved an accuracy of at least 75%.
It did not seem possible to achieve this with this model. 

The best optimised model returned: a loss of 0.5612 and an accuracy of 0.7314

### Increasing Performance
- Data:
The grouping together of low numbers of application types and classifications under 'other' was reduced. Both of these were changed to only remove types with a value count of less than 100. When they had begun at 500+ (application types) and 1000+ (classsification).

- Layers:
A third layer was added to the model.

- Nodes: 
The nodes for each model were increased to 120 for layer one and 60 for layers two and three.

- Activation Functions:
The activation functions were kept as relu for the first two layers and sigmoid for the output layer. But the third layer proved most beneficaly with another type of activation function, consequently it uses the tanh activation.

- Epochs:
The model began with 50 epochs, but this was increased to 100, more than this was unnecessary.


## Summary
The results of the model are somewhat acceptable. It does not reach the aimed for accuracy, but it is less than 2% off. It is likely with the right changes to the model this could be further improved.

As it is, the model could still be useful for determining the likely success of applications, but some manual check might be worth doing alongside the model.

Otheriwse the results might be improved by looking into the data and changing the importance of different variables to the model. Or by trying the data with different model types e.g. keras model.
