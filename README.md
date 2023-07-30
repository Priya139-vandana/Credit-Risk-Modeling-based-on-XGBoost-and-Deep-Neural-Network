# Credit-Risk-Modeling-based-on-XGBoost-and-Deep-Neural-Network
In the world of finance and lending, credit risk modeling plays a vital role in assessing the probability of borrowers defaulting on their loans or credit obligations. 
The ability to accurately predict and manage credit risk is crucial for financial institutions to make informed decisions, maintain a healthy portfolio, and minimize potential losses.
With the advent of advanced machine learning techniques, two powerful algorithms that have gained significant popularity in credit risk modeling are XGBoost and Deep Neural Networks (DNN).
# Roadmap
The roadmap for the model development includes various milestones which are as follows:
1. Data Collection
2. Data Cleaning
3. Exploratory Data Analysis
4. Data Processing
5. Feature Selection
6. Hyperparameter Optimization
7. Model Training
8. Testing
9. Validation
10. Strategy Development
# Data Collection
In the data collection section, we are collecting the required data from various sources. The data here that has been collected is 1 year customer data who has applied for credit card and
their default rates. 
# Data Cleaning
In this section, we identify the outliers and do the outlier treatment. There are various outliers treatments that are popular, one among them min-max imputation. In this method, we identify
the outliers and the outliers which are greater than max will be replaced with the value that is 99 percentile in the overall data and the outlier which are less than min are 
replaced with 1 percentile. 
Once the outlier treatment is done, we need to clean the null values. This can be done either by excluding the null values or replacing them with either median, mode based on the 
data distribution and main objective. 
Null value treatment is not required when dealing with XGBoost as XGBoost can handle null value by itself. But in this case we are doing as we need the data for neural network as well. 
# Exploratory Data Analysis
In this section, we are exploring the data and make meaningful insights. Understanding the data is much crucial before starting the model development because the more we 
understand data we get to know if there are any relations between various variables and accordingly we might need to add a interactive variable that would help for 
converging the model better. 
# Data Processing
In this section, we are processing the data in such a way that our model can understand. Find the categorical variables and complete the one-hot encoding for those variables.
As the model can only understand the numbers we are converting the categorical variables to binary form through one-hot encoding. After one-hot encoding the number of features/columns 
would have been increased to a greater extent. 
# Data Sampling
In order to avoid the problem of over-fitting we are splitting the dataset into 2 or 3 datasets. So we train the model with 1 dataseta and test with the other 2 datasets. This also 
helps us to identify the predictive capability of the model in dynamic environments. 
# Feature Selection
As the one-hot encoding must have ended us with 100+ features, it is quiet complex for the model to converge and it is our duty to make the model more simplex by providing only the
input variables that are most relevant for the target variable. In this section, we are running XGboost Models atleast 2-3 with various parametes and find the feature importances for all the variables.
Consider taking the features that are available in all the 3 models for the final model training. 
# Hyperparameter Optimization
As we have already reduced the features, the next step in our model development is to identify the hyperparameters that gives the optimum solution that is more accurate and precise. 
There are various techniques for them like RandomSearch, GridSearch, and Bayesian Optimization. Depending upon the number of features that are available in your model you can choose the optimization
technique. Bayesian Optimization is the most popular among them as the computational capacity required for it is very less compared to others. To still further increase the computational spedd
we can create a DMatrix with the required X & Y Variables and pass it as input for the Bayesian Optimization. On completing the Bayesian Optimzation we will get the required optimum
hyperparameters. 
# Training
After obataining the required hyperparameters from the previous section use them to train the train dataset and find the feature importances for the variables
# Testing
Use the same hyperparameters with test datasets and find the probability of the default rate. 
# Validation
In this section we are using confusion matrix to validate the precision, accuracy of the model. Since we have applied the model on the test dataset find the confusion matrix 
for these datasets and check the precision and accuracy
# Strategy
This is the most important part for the credit risk modeling. Once the model is developed, we are supposed to communicate to the business what is the optimum threshold value for the
default rate that the business can consider. For example, if the threshold is set at 0.5, then the credit card applicants whose probability of default falls greater than 0.5 would be
rejected for the credit card. This would be loss for the business as we are rejecting and on the other side there might be some customer whose probability is less than 0.5 but 
they have defaulted in actual which would be a loss to the business as the applicant hasn't paid the credit card bill. So we need to find the optimum threshold probability that
best suits the business by generating more revenue with good profits. 
There are two ways to approach this
1. Conservative Strategy
2. Aggressive Strategy
# Conservative Strategy
In this strategy, our main objective would be to reduce the loss that is being generated due to the failure of credit card payments. This case would require the threshold as low as possible. So that the applicants whose default rate probability below this would be accepted. 
# Aggressive Strategy
This strategy concentrates on increasing the number of applicants by keeping the default rate at a higher level. So that the number of customers being accepted for credit card would be high
