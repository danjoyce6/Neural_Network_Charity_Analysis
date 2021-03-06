# Neural_Network_Charity_Analysis
Pandas, Scikitlearn, Tensorflow, Keras

## Overview
The purpose of this analysis was to create a neural network using Pandas, SciKitlearn, Tensorflow, and keras for Alphabet Soups business team using a CSV with information regarding funding to develop a working model that would predict success of the funding.  Data was cleaned and preprocessed prior to model development using Pandas and Scikitlearns One Hot Encoder and Standard Scaler to normalize the data.  A neural network model was created that predicted success at a moderate level of using the data provided.  Attempts were made to optimize the model to better predict success of the funding with minor improvements to the original model.

### Resources
charity_data.csv

### Tools Used
Jupyter Notebook
Pandas
Scikit-Learn
Tesnorflow
Keras
OS

## Results
### 1. Data Preprocessing
  - After reading in the data frame and considering the purpose of the analysis, the target variable of the model was considered the variable "IS_SUCCESSFUL".  This was a binary variable that classified the success of funding as a 0 or 1.  This was defined as the y variable for the model and no preprocessing was necessary for this variable.
  - ![image](https://user-images.githubusercontent.com/88444529/148570426-93bbdd39-6616-44b4-bdbe-07fad2714fc0.png)
  - Two variables were dropped that were determined would not contribute valuable information as a feature to the model.  Those features were determined to be "EIN" and "NAME".  Neither of these variables contributed information to the model and were dropped during preprocessing.
  - ![image](https://user-images.githubusercontent.com/88444529/148570787-9b522285-901f-403f-ada1-b8f4475f2a5f.png)
  - The rest of the variables were considered the features inclduing "APPLICATION_TYPE",	"AFFILIATION".	"CLASSIFICATION",	"USE_CASE",	"ORGANIZATION",	"STATUS", "INCOME_AMT",	"SPECIAL_CONSIDERATIONS", and	"ASK_AMT".  Density plots were used to evaluate and analyze how to appropriately bucket the features.  Two features ("APPLICATION_TYPE" and "CLASSIFICATION") contained more than 10 unique values and were bucketed to contain six unique values.  During the optimization attempt, the "INCOME_AMT" variable was also bucketed to create less unique values as in the original model.
  - ![image](https://user-images.githubusercontent.com/88444529/148571460-b72e9af0-5abb-4f8b-ab14-5af7948ac382.png)
  - ![image](https://user-images.githubusercontent.com/88444529/148571497-10fdee13-f38c-4e09-981a-695c6c9979dc.png)
  - ![image](https://user-images.githubusercontent.com/88444529/148572781-8f3dba3f-b695-4112-b646-a9b54c192ae7.png)
  - The categorical variables were put into their own list from the original dataframe and OneHotEncoder was used to encode the categorical variables into numeric binary variables.  The resulting dataframe with encoded values was merged into the original dataframe and the variables were then dropped.  A StandardScaler instance was created and all of the features were standardized after creating training and testing variables.
### 2.  Compiling, Training, and Evaluating the Model
  - 100 neaurons were selected for the first hidden layer with an activation function of relu, which was between 2-3 times as many features as in the model.  60 neurons were selected for the second hidden layer and approximately half of the number of neurons in the first hidden layer in an attempt to optimize the model, which is 20 more than were selected in the first run of the model.  During optimization the relu activation function was chosen for each of the hidden layers.
  - Optimization was unable to yield a model with 75% accuracy.
### 3. Optimization
  - During optimization multiple attempts were made to increase the accuracy of the model.  One step that was taken was to reduce the number of unique values in the "INCOME_AMT" variable by filtering all of the values of 10M or greater into one variable.  Another step that was taken was to increase the number of neurons in hidden layer 1 and hidden layer 2 to 100 and 60 respectively.  An additional step was taken to increase the accuracy of the model by increasing the epochs to 500.  The results after these changes did not yield a model that reached 75% accuracy, and was instead 72.5%.  Other attempts and changes were made that did not increase the model accuracy as well including using the tanh function for hidden layers, sigmoid for hidden layers, and varying numbers of epochs but none of the changes resulted in a more accurate model.
  - ![image](https://user-images.githubusercontent.com/88444529/155038408-bb6fdc46-b5b5-4d98-ae7f-4a925cefd297.png)
  - ![image](https://user-images.githubusercontent.com/88444529/155038477-ff1a74a4-ad2b-4d1f-b8cb-f31f71e12e6f.png)
  - ![image](https://user-images.githubusercontent.com/88444529/155038509-aa2a154a-ccb8-461f-af4f-7cafaf74ffd5.png)

## Summary
The neural network that was created yielded a 72.5% accurate model while the optimized model came produced an identical accuracy metric of 72.5%.  Both models failed to reach the 75% threshold.  Future models may want to do future analysis to see if some variables should be weighted more or not standardized.  Another option that future analyses could direct attention to is utilizing a random forest model or support vector machine instead of a neural network, as these can be just as accurate as neural network models under some conditions.  Although this analysis did not yield the appropriate results, it did provide insight into the dataset and ways that the model could be improved to create a model that could better predict success of the funding from Alphabet Soups business.

### Contact Information
email: danjoyce6@gmail.com
