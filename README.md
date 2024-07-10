# ML 
Applicable data format: Variables extracted from remote sensing images were used as independent variables, and measured soil organic carbon content was used as dependent variable. In the Excel table, the first column is measured organic carbon content, which is named SOC, and the rest is listed as remote sensing variables, such as NDVI,NDWI, etc

This code is used for machine learning to build predictive models, variable importance analysis and 1:1 line output of measured and predicted values (RF\BRT\XGBOOST)

The main steps are as follows:

A.  The original data is randomly divided into a training set and a test set according to 7:3. The training set is used to build the machine learning model, and the verification set is used to evaluate the generalization ability of the model.

B.  Based on training set data, find the most suitable parameters of the machine learning model, RF including mtry and ntree, BRT including n.rees, interaction.depth, shrinkage and n.shrinkage node, XGBoost includes nrounds, nrounds, eta, gamma, colsample_bytree, min_child_weight, and subsample.

C. Define a function whose input parameters are different seed numbers. The main body of the function is based on the best parameters found in step B and uses the input seed number to build multiple machine learning models, and outputs precision parameters to the established machine learning model. For example, if 100 different seed numbers are input, a model of 100 times will be established, and the average value of the accuracy evaluation index of the 100 times model will be taken as the evaluation result of the model, and the accuracy index will be output. This prevents the model from being affected by random seed numbers.

D. The seed number is consistent, and 100 models established in step C are executed again. The predict function is used to input the independent variables of the test set, predict the dependent variables of the test set, and conduct 1:1 line mapping with the measured values.

E. The number of seeds remains the same, and the 100 models established in step C are executed again to output the relative importance of each variable in each model, and the relative importance of each variable is obtained by adding and normalizing the relative importance of each variable.

F. Use the established machine learning model to predict the dependent variables in the whole study area based on the variables extracted from the whole study area, and output the predicted value.

DATA:
[ML_DATA.xlsx](https://github.com/user-attachments/files/16126162/ML_DATA.xlsx)
[ID+SOC+Longitude+latitude.xlsx](https://github.com/user-attachments/files/16154366/ID%2BSOC%2BLongitude%2Blatitude.xlsx)
[document description.txt](https://github.com/user-attachments/files/16126228/document.description.txt)

