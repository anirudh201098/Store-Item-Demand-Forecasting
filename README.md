# Store-Item-Demand-Forecasting
## Mission statement: 
A data science project for demand analysis of items in stores. The data is a multiple time series data where we have 500 sets of combinations for stores and items, and we are required to analyse them and forecast their future values.

Dataset: [Store Item Demand Forecasting Challenge (Kaggle)](https://www.kaggle.com/c/demand-forecasting-kernels-only/data)

## Procedure
We use train.csv which contains 5 years of sales for 50 items in 10 stores, from 2013 to 2017.
There are 10 stores and 50 items. Sales are given for each item in each store, i.e. 500 sets of sales, each of 5 years.
Values of sale range from about 2 to 50.

## Data Visualization
#### Store-wise and Item-wise sales arranged according to maximum sales
<img src="https://github.com/anirudh201098/Store-Item-Demand-Forecasting/blob/master/Data%20Visualization/Screenshot%20(251).png"  width="1200" height="600">

#### Day-wise and Month-wise and Year-wise sales

<img src="https://github.com/anirudh201098/Store-Item-Demand-Forecasting/blob/master/Data%20Visualization/Screenshot%20(252).png"  width="800" height="300">

#### Item-wise and Store-wise sales

<img src="https://github.com/anirudh201098/Store-Item-Demand-Forecasting/blob/master/Data%20Visualization/Screenshot%20(253).png"  width="800" height="300">

### Feature selection:
#### Categorical Embedding
The task of entity embedding is to map discrete values to a multi-dimensional space where values with similar function output are close to each other.
After we use entity embeddings to represent all categorical variables,  all embedding layers and the input of all continuous variables (if any) are concatenated.
The merged layer is treated like a normal input layer in neural networks and other layers can be build on top of it. With entity embedding we want to put similar values of a categorical variable closer to each other in the embedding space.
After adding embedding layers for year, week of the day, day of the week and month of year, extracted from date feature. We also added embedding layers for stores and items. Then we concatenated all the embedding layers, which resulted in 62 unique features after eliminating the redundancy.

#### Train, Test and Validation sets:
We considered 2017 as our test data, and 2013 -2016 as our train data. The train data has 7,30,500 samples, and test data has 1,82,500 samples.
For validation, we considered leave 6 out strategy, wherein 6 months is used as validation data and rest of the 42 months is used for training each set of samples. We fine tuned the results considering different 6 months in each year.

### Deep models
In this category, after concatenating all the embedding layers, we applied Neural Networks, Long Short term Memory (LSTM), Temporal Convolutional Neural Network (TCN), Hybrid model (TCN +LSTM), and LSTM Autoencoder.

#### Other techniques 
Fbprophet 

### Predictions on Deep models

#### Predictions of Neural Networks evaluated by R2 score
<img src="https://github.com/anirudh201098/Store-Item-Demand-Forecasting/blob/master/Data%20Visualization/Screenshot%20(254).png"  width="800" height="300">

#### Predictions of LSTM evaluated by R2 score

<img src="https://github.com/anirudh201098/Store-Item-Demand-Forecasting/blob/master/Data%20Visualization/Screenshot%20(255).png"  width="800" height="300">

Similarly, we have plotted graphs for TCN, Hybrid model and LSTM Auto encoder


### Predictions on Other techniques

#### Predictions of Fbprophet evaluated by R2 score, MAPE, MAE
<img src="https://github.com/anirudh201098/Store-Item-Demand-Forecasting/blob/master/Data%20Visualization/Screenshot%20(259).png"  width="800" height="300">

