## Predicting Stock Closing Prices of MAANG Companies using LSTM and Linear Regression

**Project description:** This project was completed as the final project for MAT 128B at UC Davis and was completed with a partner. The goal of the project was to predict future stock prices of Meta, Amazon, Apple, Netflix, and Google (MAANG) using historical stock prices. If successful, the model could be used to decide when to buy or sell stocks to make a profit. Two models were created, one Long Short Term Memory (LSTM) model and one linear regression model. The linear regression model preformed better. However, both models were unable to predict accurately outside a short time span since the stock market is heavily influenced by external factors. 
This project consisted of four phases; basic data analysis, model building, model evaluation, and model refinement. 

### 1. Basic Data Analysis

Python was used to generate visualizations of the spread of the data and the relationships between features. In particular, a correlational matrix showed a stock's open, close, high, and low price were strongly correlated. The volume of stocks bought was also strongly correlated to the price. 
As such, the closing price was used as the feature of interest.  

<img src="images/CorrMatrix (1).png?raw=true"/>

### 2. Model Building

I worked on developing the LSTM model. The model was designed to work with all 5 companies, taking One-Hot Encoded company labels as input as well as historical stock closing prices. Below, you can see the basic model structure. The model was created in Python using the PyTorch package. Hyperparameter tuning on batch size, number of hiden layers, dropout, regularization parameter, and more was performed to optimize the performance of the LSTM model. 

<img src="images/LSTM_diagram.png?raw=true"/>

### 3. Model Evaluation

The model performed well on the test data (MSE: 0.0007223, R<sup>2</sup>: 0.9740), which you can see in the diagram below. This suggests the model has good performance predicting tomorrow's stock prices. However, the model failed to predict future stock prices by iteratively taking output from the model as input. When predicting further into the future, it showed an overall decreasing trend before converging to a constant value. This can be seen in the second figure below. 
While the linear regression model performed better on test data, it had the same problem predicting future stock prices. Both models accurately predicted the peaks and troughs of future stock prices, highlighting the overall pattern of fluctuations of the stock market. 

<img src="images/LSTM_test.png?raw=true"/> <img src="images/LSTM_prediction.png?raw=true"/>

### 4. Model Refinement

Two  models were created as alternatives to the ones above. One was an LSTM model trained on weekly data, hoping to predict general trends rather than the day-to-day fluctuations. However, this model performed worse on test data, and displayed a similar decreasing trend as the above models when predicting future data. 
The other was a linear model trained on the difference between yesterday's and today's price (rather than the normalized version of today's price). The goal was to predict an increase or decrease in stock price rather than predicting the exact price. However, the model overfit the data and performed poorly. It was thus not used for future stock price prediction. 

 
