# Neural_Network_Charity_Analysis
# Overview
In this module challenge, we are looking at the funds distributed by a charitable organization and the effective use of those funds. Our purpose is to find a way to best 
predict whether or not those transactions are fraudulent by using a neural network to dermine patterns and flag possible future fraud. How I will be doing this is by a 
records of past transactions and the factors that could possibly be determined to flag those that are fraud and building and training a model to determine the how 
possiible would it be that requests with a similar profile could also be fruadulent.

# Results
The Features of this model include Application type and Classification which are internal codes used to bucket the request types, the affiliation of the request, Use 
case for the request, the request amount, the income amount of the requestee's organization, type of oganization, active status, and if there are any special 
considerations

Unique Values Output:
![unique values ASC code](https://user-images.githubusercontent.com/109875421/208029102-d852ddad-c9fc-44fc-bf13-6f7d80d64552.png)
The list of features originally included EIN and Name as well, which were not useful for analysis and removed. Additionally, the ask amount and special considerations 
are noisy and are extra variables that are likely confusing our model and could be removed in order to improove accuracy.

# Compiling, Training, and Evaluating the Model
Originally, for my first attempt,I built the model with 2 hidden layers. The first one had 90 neurons and the second had 60. I used Relu as the activation function. This 
combination made sense to myslef because we have non negative values, and Relu is generally more accurate with data of this nature. The output layer is using the sigmoid 
activation which works well for classification. By the end, there were 15,331 total parameters.
![first model attempt ASC module 19 challenge](https://user-images.githubusercontent.com/109875421/208029994-d1b9b24e-0701-4930-9a54-76045c889023.png)
However, even with all of my consideration, I was not able to achieve a 75% accuracy:
![Attempt 1 Accuracy ASC Module 19 Challenge](https://user-images.githubusercontent.com/109875421/208030644-6958ada8-cdc7-4a75-ac83-fa4f553e5efa.png)

Since, I did not reach a 75% accuracy threshhold, I decided to add a third layer and increase the neurons and to icrease the nodes for the original two layers to 90 and 
60 respectively. This doesn't innately increase the accuracy of any dataset, but in some cases it can raise the accuracy of your model.Throught this second attempt, 
there were many features I tried and giving the model more layers and neurons to see if having more data to train would improve the overall accuracacy. 
![Attempt 2 Three layer model ASC module 19 Challenge](https://user-images.githubusercontent.com/109875421/208031749-d6f73813-937f-43af-b94a-530dfc184d34.png)
However my accuracry did not grow by the end of the second attempt, but it also did not fall. 
Model Results Below: 
![Attempt 2 Three layer model Accuracy Results ASC module 19 Challenge](https://user-images.githubusercontent.com/109875421/208032147-a459c427-4b6f-4646-b629-3c5dbb8dd825.png)

With Relu giving me a similar readings, I thought I should change the activation function in this third and final model. I changed the avtivation function to tanh to 
see if this would help approaching how the model is working through the data. I also removed the third layer from the third attempt to see if maybe "less is more", but 
I did have the highest nodes for this last attempt to create a model with 75% acccuracy. 
![Attempt 3 Dual Layer Model ASC Module 19 Challenge](https://user-images.githubusercontent.com/109875421/208033014-70c82ee9-013b-47ae-a32e-56a2a9376b4f.png)
However as you can see below, again there was no change in my total accuracy and I did not reach an accuracy of 75%, but of roughly 73% with every permutation of this neural network model. 
![Attempt 3 Dual Layer Model Accuracy Results ASC Module 19 Challenge](https://user-images.githubusercontent.com/109875421/208033537-ba0a547e-51fa-47a4-8fbb-6d98b1f9a5ce.png)

# Summary
Overall, an accuracy score of 73% is better than a coin flip and could give this charity a better idea of which requests require more time and consideration. There are 
many features in this model, and the "black box" of deep learning and building neural networks does make it difficult without a lot of trial and error to be able to 
see which factors specifically are contributing the most to the accuracy score of any given model. Since this is a binary classification where we know the output, it 
may be more effective and simpler to go with a supervised machine learning model. Potentially a logistic regression model as this would also allow for the programmer 
to look at the coefficients and remove or modify specific disrupting factors from the model in the features.
