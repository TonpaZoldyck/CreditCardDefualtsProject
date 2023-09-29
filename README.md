## CreditCardDefualtsProject
This is th modelling and analysis of a banks credit card customers, for creating a supervised learning algorithm to accurately predict defualts in future customers

# 1 Indtroduction
The aim of this report is to explain in detail the code developed to perform machine learning algorithms for prediction of Credit Card Default. There will be a description of the first steps taken to analyze and understand the provided ‘Credit Card’ Data, as well as every manipulation and transformation applied before undertaking a series of model approaches. Descriptions on these models, as well as their pros and cons, will be discussed. A section regarding the rationale behind the validation techniques performed will follow, continued by a summary of the results obtained, their limitations and possible improvement techniques. Finally, the best performing machine learning models will be used on the test data set, which provided successful ‘recall’ scores of around 35-40%. This is one of the oldest and most useful machine learning finance applications, as significant risk can be identified early on and reduced by banks, governments and any other entity subject to capital loaning. 


# 2 Methodology Overview 
Before initiating the methodology description, it is key to mention that codes, approaches and models have been inspired by a diversified set of sources: DataCamp online courses and various YouTube videos on Supervised Learning have been studied to obtain a first insight on these type of machine learning problems. Furthermore, multiple online sources and machine learning books have been consulted to obtain final versions of the code and report. These are mentioned throughout the report and referenced at the end. The following section will discuss the approach followed to obtain the final algorithms and their corresponding results. 

For our analysis, we wanted to identify what features were important in making predictions for our dataset. Feature selection is an important machine learning technique for a few reasons. Firstly, many features within a given dataset do not provide much, if any, signal when it comes to predicting a variable - these features simply add to the noise of the data which leads to overfitting. Of course, the issue then becomes which features are important and which are not - if we remove too many features or too important ones, we then lose some of our signal which leads to underfitting. 

There are many different feature selection and dimensionality reduction techniques in machine learning each with their own pros and cons. Our strategy is to apply multiple different strategies (discussed below) and models on our data set and use the information in combination to identify which of the features are important when it comes to predicting defaults. Then we can identify which variables are consistently of most and least importance using different feature selection methods. 


# 3 Results 
After we used cross-validation to tune our hyperparameters, we used these tuned models and applied them to our data using cross-validation, with k = 5. Due to the reasons explained earlier, the evaluation metric we chose to apply is Recall. 

We first applied each tuned model to the original feature set and then did the same with engineered features to compare both. There were minimal differences between the two feature sets for most of the models. When we compare the different models, we notice that the best performer in terms of recalling defaults was the Gaussian NB. A potential reason for this could be that the features chosen are conditionally independent (as we have removed correlated features, this is more likely to be the case). When features are less dependent the Naive Bayes outperforms other models. It is important to observe that SVM gave surprisingly inaccurate results with the tuned hyperparameter C=3 (see Table 4). This model’s performance was studied individually with C=50, obtaining the recall values shown in Table 3. The recall value for SVM-Not Default could not be obtained as ‘C’ is a very computationally expensive value and the code took an excessive amount of time to run. Thus, ‘C’ was not tuned on a GridSearchCV. 

-- See Report "PREDICTING CREDIT CARD DEFAULT" for full details






