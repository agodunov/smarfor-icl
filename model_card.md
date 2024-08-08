# Model Card

The models were created as a part of my small educational project during my studies of [ML/AI at Imperial College Business School](https://www.imperial.ac.uk/business-school/executive-education/technology-analytics-data-science/professional-certificate-machine-learning-and-artificial-intelligence-programme/online//). 

## Model Description

All models accept the dataset.xlsx wich stores Pandas dataframe with 30 features from economic and stock indicators and two last columns with predictors: the future gradient of 20 days price moving average and the sign of this gradient. The same file can be used for classification or regression modelling. As a training exercise, I had to pickup three models from the program I studied, so my choice was the following:
1. **Logictic Regeression**. This is the most simple model implemented using LogisticRegression class from sklearn python module. The model is simple and I pick it up to get the result as quickly as possible. The module return the result_lr.xlsx with the last column "Prediction" and values +1 or -1 which simply means the direction of the market. The model tries to improve generalization via regularization constant but it seems not required. 
2. **Decision Tree** - I pickup this model because of transparency, explainability and flexibility. It returns the forecasted direction of market +1 and -1, tries different depths but most importantly provides the analysis and insight which features contribute the most into the prediction.
3. **Neural Network** - I pickup the fully connected Neural Network as the most advanced model although with less transparency. It requires pytorch module to be installed in Python and it uses GPU to speed up the calculations. The Neural Network has the architecture  of 4 layers with the following activation functions: $$ ReLU - Sigmoid - Sigmoid - Sigmoid $$ 
The number of 28-27-22-19 neurons was selected in the result of Bayesian Optimization of hyperparameters. The model calculates the loss function as L2 norm of forecasted ${MA}_{20}$ gradient, because it allows a more granular fine-tuning than Accuracy. The Accuracy is calculated for the optimized model just to compare with previous models.

## Performance

### Logistic Regression
The Accuracy of Logical Regression for the train data is 77.2% and 76.8% for the test data. 
#### Decision Tree 
The maximum depth of the Decision Tree model was chosen to be 13 levels, which gives 95% of accuracy for training data and 80.2% on the test data.
#### Neurol Network 
The neural network with the optimal architecture 28-27-22-19 shows an incredibly good result: on training data, the accuracy was 98%, and the accuracy of market prediction on test data was 95.1%
## Limitations
* These models is not for trading due to lack of last month data in FRED database
* You have to use python 3.8 due to compatibility issue with FRED API
* The LR and NN models are sensitive to the scaling of features, therefore if the market reveals an unusual pattern then the performance might be worse than expected.
* The result is too good so it should be necessary to investigate if it was a leakage of information from future, during revisions of past economic  indicators by the government.
