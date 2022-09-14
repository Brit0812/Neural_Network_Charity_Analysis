# Neural_Network_Charity_Analysis
# Overview 


The purpose of this project is to use of machine learning and neural networks.  Neural networking is incredibly important as it used for predictive modeling and its adaptability, since it’s actively learning from its previous trained dataset. 

In order to take full advantage of neural networking the data must undergo preprocessing, which transforms the data so it can be easily read into the network. After the data was transformed it will be placed into ta model that will then be trained and evaluated. Once that step is complete and a rough idea of the model’s loss and accuracy is, the model will then undergo revisions to improve its output. 

#Results
•	Data Preprocessing
o	The variable that was considered the target of the model was IS_SUCCESFUL as it provides clear data on the charity donation. This makes it the dependent variable as it’s the outcome of the other columns. 
o	The rest of the columns were considered the features for the model as they had an impact on the whether or not the charity donations were successful. This makes them the independent variable. 
o	The columns that were removed were EIN and NAME since they hindered the data with clutter, it provided no useful input. 

images of the preprocess 

•	Compiling, Training, and Evaluating the model
o	For the initial neural model there were two hidden layers. The first layer had 80 neurons while the second had 30. Both layers used the relu activation function. The output layer had 1 neuron and utilized the sigmoid activation function. 
o	None of the altered models were able to reach the 75% target, while the initial model had an accuracy of 63%. 
•	In order to optimize the model to reach its target multiple steps were taken, the first was removing any additional noisy features(columns) such as ‘USE_CASE’ and ‘ORGANIZATION’. These 2 columns were removed since they wouldn’t provide much influence to the data.  This was applied to the following models: 
o	ATTEMPT #1:
	The total of neurons was increased. In the first hidden layer, the neurons were increased to 120, the second hidden layer was increased to 50, and the epoch was increased to 120 as well.  These corrections had a huge improvement on both the loss and accuracy on the model. 

Image attempt 1 summary 

o	ATTEMPT # 2 
	Another attempt to increase the accuracy of the model would be to add another hidden layer. The layers followed attempt # 1 (120, 50), rather than the initial run through (80, 30) The epoch was also increase, slightly.  This attempt didn’t improve neither the loss nor the accuracy. 

Image attempt 2 summary 

o	ATTEMPT # 3 
	The activation function was changed from “relu” to “tanh”, with the same conditions as the first attempt. This attempt was the worst of all them all, as the accuracy plummeted to 38%. 

Image attempt 3 summary

o	ATTEMPT # 4 
	The total of neurons was decreased. In the first hidden layer, the neurons were decreased to 45, the second hidden layer was increased to 15, and the epoch was increased to 135.  These alterations improved the accuracy to 71%, but the loss increased dramatically. 

Image attempt 4 summary


# Summary 

The final attempt had the lowest optimization standing at 71%, but the loss (1.4) proves to be troublesome. If one were to take into the consideration the initial run the accuracy was 63% with a very high loss (1.4). In this case, since the losses are similar the accuracy did show a huge improvement. The loss could be high due to overfitted, which is detrimental to neural network models. In order to prevent overfitting, the removal of more noisy features, increasing the amount of data, and bucketing of ASK_AMT. If one were to bucket the ASK_AMT, it wouldn’t be as simple as saying IF the count has less that X amount it will be categorized as other. When this is done it has a massive impact on the data, as it’s binning nearly 1/3 of the data into the “other”. It would be ideal place a range for the ASK_AMTs, such as: 0-4999, 5000-9999, and so on. The best model to use may have been the Random Forest Classifiers as it doesn’t require scaling, but it could be implemented. Random Forest is a lot faster to run and, in this instance, could have prevented possible overfitting.   
