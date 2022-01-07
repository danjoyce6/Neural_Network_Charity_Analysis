# Neural_Network_Charity_Analysis
Pandas, Scikitlearn, Tensorflow, Keras

## Overview
The prupose of this analysis was to create a neural network using Pandas, SciKitlearn, Tensorflow, and keras for Alphabet Soups business team using a CSV with information regarding funding to develop a working model that would predict success of the funding.  Data was cleaned and preprocessed prior to model development using Pandas and Scikitlearns One Hot Encoder and Standard Scaler to normalize the data.  A neural network model was created that predicted success at a moderate level of using the data provided.  Attempts were made to optimize the model to better predict success of the funding with minor improvements to the original model.

## Results
- Data Preprocessing
  - After reading in the data frame and considering the purpose of the analysis, the target variable of the model was considered the variable "IS_SUCCESSFUL".  This was a binary variable that classified the success of funding as a 0 or 1.  This was defined as the y variable for the model and no preprocessing was necessary for this variable.
  - ![image](https://user-images.githubusercontent.com/88444529/148570426-93bbdd39-6616-44b4-bdbe-07fad2714fc0.png)
  - Two variables were dropped that were determined would not contribute valuable information as a feature to the model.  Those features were determined to be "EIN" and "NAME".  Neither of these variables contributed information to the model and were dropped during preprocessing.
  - ![image](https://user-images.githubusercontent.com/88444529/148570787-9b522285-901f-403f-ada1-b8f4475f2a5f.png)
  - The rest of the variables were considered the features inclduing "APPLICATION_TYPE",	"AFFILIATION".	"CLASSIFICATION",	"USE_CASE",	"ORGANIZATION",	"STATUS", "INCOME_AMT",	"SPECIAL_CONSIDERATIONS", and	"ASK_AMT".  Density plots were used to evaluate and analyze how to appropriately bucket the features.  Two features ("APPLICATION_TYPE" and "CLASSIFICATION") contained more than 10 unique values and were bucketed to contain six unique values.  During the optimization attempt, the "INCOME_AMT" variable was also bucketed to create less unique values as in the original model.
  - ![image](https://user-images.githubusercontent.com/88444529/148571460-b72e9af0-5abb-4f8b-ab14-5af7948ac382.png)
  - ![image](https://user-images.githubusercontent.com/88444529/148571497-10fdee13-f38c-4e09-981a-695c6c9979dc.png)
  - ![image](https://user-images.githubusercontent.com/88444529/148572781-8f3dba3f-b695-4112-b646-a9b54c192ae7.png)
  - The categorical variables were put into their own list from the original dataframe and OneHotEncoder was used to encode the categorical variables into numeric binary variables.  The resulting dataframe with encoded values was merged into the original dataframe and the variables were then dropped.  A StandardScaler instance was created and all of the features were standardized after creating training and testing variables.
- Compiling, Training, and Evaluating the Model
  - 100 neaurons were selected for the first hidden layer with an activation function of relu, which was between 2-3 times as many features as in the model.  60 neurons were selected for the second hidden layer and approximately half of the number of neurons in the first hidden layer in an attempt to optimize the model, which is 20 more than were selected in the first run of the model.  During opti
