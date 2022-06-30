# Neural_Network_Charity_Analysis

## Overview of the analysis: Explain the purpose of this analysis.

This was one of the most complicated analyses I have performed to date. This analysis has a lot of moving parts. This analysis was a mulit-step deep dive into Neural Networks and deep machine learning. In this analysis, we familiarized ourselves with all aspects of building a neural network utilizing input layers, output layers, hidden layers, activation, neurons, the Keras tuner, OneHotEncoder, and optimizing our models. 

The challenge required us to preprocess data from a CSV file, identify the target and features, compile, train, and evaluate a model, optimize a model, as well as modifying the model to find the best accuracy. As I worked through the challenge, it became clear that more is certainly not always better with neural networks. 

The scope of the analysis was as follows:

"From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization."

## Results:

### Data Preprocessing

- What variable(s) are considered the target(s) for your model?
For this analysis, the target or dependent variable for my model was the column, "IS_SUCCESSFUL," which had the values of 1 or 0. "Is Successful" answered the question "Was the money used effectively?"

- The following variable(s) are considered to be the features for the initial model:

    - APPLICATION_TYPE—Alphabet Soup application type
    - AFFILIATION—Affiliated sector of industry
    - CLASSIFICATION—Government organization classification
    - USE_CASE—Use case for funding
    - ORGANIZATION—Organizat ion type
    - STATUS—Active status
    - INCOME_AMT—Income classification
    - SPECIAL_CONSIDERATIONS—Special consideration for application
    - ASK_AMT—Funding amount requested


- What variable(s) are neither targets nor features, and should be removed from the input data?

  - EIN
  - Name

### Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network model, and why?

For the initial analysis, I used two hidden layers. For each of these layers, I chose to start with fewer neurons. For the first layer, I chose 10 neurons and for the second hidden layer, I chose 5. I chose reLU for the input layer and for the two hidden layers. I chose sigmoid activation for the output layer. I chose these parameters because I wanted to start off with a simple model to see if adding to it and modifying it would make it improve performance. 

----
![Compile, Train, Evaluate](https://github.com/lllohr/Neural_Network_Charity_Analysis/blob/13ffcc85650c136a2471a19919a44baed096ba88/Resources/images/D2_Compile_Train_Evaluate.png)

----

- Were you able to achieve the target model performance?

I attempted many different models and was not able to achieve performance higher than an accuracy of 0.7239649891853333. 

----

![Best Model Performance](https://github.com/lllohr/Neural_Network_Charity_Analysis/blob/13ffcc85650c136a2471a19919a44baed096ba88/Resources/images/Deliverable1_2_Evaluate.png)

----

- What steps did you take to try and increase model performance?

I added nodes, I added layers. I removed features to just a few variables. I utilized KerasTuner to attempt to improve performance. I changed the activation of each layer. I optimized the model. However, there was not any significant improvement with any of these methods. In fact, most methods that were pursued significantly decreased the accuracy. 

## Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

What I found with this analysis was that the more layers I added, the more nodes/neurons I added, did not equate to better accuracy. When I removed features from the model, it actually degraded the performance significantly. I created a model with 8 hidden layers, which resulted in much improved loss statistics: 2.2945218086242676, but a significant decline in accuracy: 0.46775510907173157. I did use the KerasTuner to attempt to find a more accurate model but was completely unsuccessful.
- - - -

![8 Layers](https://github.com/lllohr/Neural_Network_Charity_Analysis/blob/665efb7e18bac8208f3698d771e3a25d7202460d/Resources/images/8_layers.png)

- - - -

![8 Layers Parameters](https://github.com/lllohr/Neural_Network_Charity_Analysis/blob/ea7c156b9f87e50b282502e555c857f9184dfea2/Resources/images/8_layers_parameters.png)

----
My recommendation for this classification problem would be to try a random forest classifier or SVM (Support Vector Machine) to compare the accuracy. I think one of those models could do a better job. According to our literature, "SVMs are less prone to overfitting because they are trying to maximize the distance, rather than encompass all data within a boundary." I suspect that there may be some better way to tackle this dataset. 
