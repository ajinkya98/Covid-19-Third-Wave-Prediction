# Covid-19-Third-Wave-Prediction

## Problem Statement:

Covid-19 is a rising pandemic which has plagued the planet since the last two years. Through this project we want to make analysis of the trends for the Covid-19 test cases pattern, in order to better help the healthcare system for them to prepare for severe outage of Covid-19 cases. One of the major problems that occurred during the first and the second wave of Covid-19 especially India [this is an important point to analyze as the dataset is from India.] was the shortage of beds and oxygen cylinder for the serious Covid-19 patients. Thus, having this kind of analysis and prediction can help better prepare the health care companies to better handle the pandemic. Through this project we propose to estimate the number of Covid -19 new cases in the third wave. In order to compare the performance of our machine learning model we will be using state of the art evaluation techniques to gauge the robustness of the model. Also, since the third wave has passed by India, we will also be using the real data and plot it against the predicted data to see the performance of our model in a visual manner.

## Proposed Model:

<img width="587" alt="Screen Shot 2022-06-05 at 8 56 35 PM" src="https://user-images.githubusercontent.com/32778343/172078206-87c1aa4a-41cd-4f9f-9365-afb542c1d7bf.png">

The proposed model for the project is the Long-Short Term Memory Deep learning model. It is a powerful deep learning architecture popularly used for time series prediction. The reason for its popularity is that it does not suffer from the problem of vanishing and exploding gradients or in layman’s terms it can capture the temporal information of a dataset with great accuracy and over extended periods in the timeline of the dataset. This model will help us solve the regression problem of predicting new cases after training on the dataset. We will also compare the performance of these models to other popularly used machine learning models to draw a comparative analysis.
 
The LSTM model works on the principals of the gating mechanism mimicking a circuit like behavior controlling the flow of information. The LSTM model accepts a stream of data as input and outputs the prediction for the next timeline. This way the model usable to perform immensely great on problems requiring temporal information retaining like time series analysis and NLP problems that entail retaining long sequences of words and sentences to make the next work or sentence prediction. The LSTM module consists of two major sections, one is the hidden state cell, and the other is a cell state. The hidden state is responsible for retention of immediate inputs, or the the current inputs as depicted in the figure above, whereas the cell state retains information pertaining to older sequences and are crucial in deciding what part of the information is stored before passing the next input to the LSTM model. The gating mechanisms are nothing but activation functions like sigmoid and tanh that shrink values between 0 and 1 and -1 and 1 respectively. Other operation includes the addition or concatenation depicted by the plus sign and dot product represented by the cross in the diagram. It must be noted that it is possible to stack two of such models wherein the intermediate output is passed on to the next stacked LSTM layer which is what we implemented in our project as well.
Data subsetting will be involved in the process as time series data has to been uploaded in batches based on the timesteps. This involves creating a 3D tensor as an input to the LSTM model. First dimension stands for the number of batches in the dataset. The second dimension stands for the number of datapoints per batch. And the third dimension is for the timesteps wherein the timestep is sliced batchwise. Length of the subgroups will be a hyperparameter which will be tuned to give the best performance. For testing the main task will involve creating the training and testing loops to train the deep learning models. The next step would involve finding an appropriate performance metrics to validate the performance of the model. For time series prediction being a regression problem, typically RMSE or root mean squared error will be used as a testing metric.

In terms of uncertainties, one of the drawbacks of the deep learning model is that despite being very powerful its interpretability is hard to overcome. It is a black box model that tunes to solve problems related to any field despite not having the domain knowledge. Thus, the uncertainty will be to find deeper trends and give reasoning for the estimation of the predicted timeline.

## Dataset Details:

The dataset has the mainly two features artificially expanded into four features. The new_cases feature column and its corresponding cumulative feature column along with new_deaths and its corresponding cumulative column. Other features like country code, unnamed, country, WHO region etc. are unimportant as this dataset is a subset of a larger world cases dataset, all entries for these columns are exactly same. So, these will be removed from the dataset before feeding the data to the LSTM model. The feature which will be used as a dependent variable is the new_cases feature as we are interested in predicting this statistic. Thus, the independent features will be the new_deaths, cumulative_deaths and the cumulative_cases columns. The dataset has certainly evolved over time as new cases over the years 2020-2022 have been updated in the dataset. As far the collection process for the dataset goes, it comes from a conglomeration of NGOs across the world who have collaborated to provide the dataset. Recollection of the data is always possible as new covid cases are rising by the day and their website is updated daily.
The dataset has been sourced from the from the following link: https://data.humdata.org/event/covid-19

## Data Management and Analysis:

The data preprocessing required for the task for minimal as dataset was sourced from a licensed open-source website and the data was clean on acquisition. However, we have plotted several figures to analyze the trends of the cases and the following observations were made:

<img width="886" alt="Screen Shot 2022-06-05 at 8 59 06 PM" src="https://user-images.githubusercontent.com/32778343/172078310-ed3f7f61-57ec-4819-ad0f-213d4c46aecb.png">

The following figures above represent the box plots for the new cases and new deaths. The box plot is essentially a percentile information figures which shows the what percent of datapoints pertain to how many new cases or new deaths. As seen from the figures above there are several outliers in both and theses are the datapoints of interest as the new cases and new deaths will rise exponentially in a Covid-19 wave. We also plotted the training data to visualize the first two Covid-19 Waves upon which the LSTM was trained to make prediction for the third wave.
As seen in the figure able the first two peaks represent the first two waves of the Covid-19 pandemic.

<img width="862" alt="Screen Shot 2022-06-05 at 9 00 08 PM" src="https://user-images.githubusercontent.com/32778343/172078360-04784736-4bf8-40bc-957a-c1f258176458.png">

## Argument:

Covid-19 is a rising pandemic which has plagued the planet since the last two years. Through this project we want to make analysis of the trends for the Covid-19 test cases pattern, in order to better help the healthcare system for them to prepare for severe outage of Covid-19 cases. One of the major problems that occurred during the first and the second wave of Covid-19 especially India was the shortage of beds and oxygen cylinder for the serious Covid-19 patients. Thus, having this kind of analysis and prediction can help better prepare the health care companies to better handle the pandemic. Through this project we propose to estimate the number of Covid -19 new cases in the third wave. In order to compare the performance of our machine learning model we will be using state of the art evaluation techniques to gauge the robustness of the model. Also, since the third wave has passed by India, we will also be using the real data and plot it against the predicted data to see the performance of our model in a visual manner. As this analysis is predicting the number of cases of Coronavirus in the future, it can be used by the healthcare professionals and government to plan the arrangements accordingly and also set rules and curbs knowing the status of the cases.This can be used to predict the future wave and doctors can benefit a lot from this as they can relate what factors are causing a rise in cases and also plan out the situation in a better way.As this is a completely trained model, our target don't need to have much of computer or programming knowledge. They just need to feed the data and understand the output in a proper way.These insights are really useful as Covid is going on since a year and a half and data science could really be an effective measure to stop it as learning about how and when the cases are rising could give us the information which will help us in stopping it.

## Ethics:

As this model predicts the future cases which could happen due to this pandemic, it needs to be secretive to the officials otherwise there would be a state of panic in the country and it would cause a lot of stress in people. We are considering the cumulative cases and deaths as our input to predict our target variable. Since this data is open source, there is no breach of privacy done here. Also this model could be used in a positive way to be prepared for a future wave but also at the same time the people could use it for politics. Our design does not affect world's resources, it might just benefit us all in case of a severe situation.

## Results:

<img width="862" alt="Screen Shot 2022-06-05 at 9 02 01 PM" src="https://user-images.githubusercontent.com/32778343/172078483-730b930b-7881-4ee2-9c6a-ddbbd83c4a94.png">

As seen from the graph above the third wave has been predicted correctly using our LSTM model. On close comparison with the true cases plot for the third wave in India, the wave matches very closely. One of the observations for the prediction is that it is slightly noisy at the peaks, that is because as good as the LSTM model is it has its own drawbacks, LSTM has been replaced with transformer models for time series based models as it can retain even longer sequences and parallelize better on modern day GPUs. Below we show the figure for the true cases plot from google.

![download](https://user-images.githubusercontent.com/32778343/172078669-98a1279f-2243-4505-be33-8d7a661e78e3.png)

## References:

-https://en.wikipedia.org/wiki/Long_short-term_memory

-https://towardsdatascience.com/the-lstm-reference-card-6163ca98ae87

-https://keras.io/api/layers/recurrent_layers/lstm/ 

-https://www.researchgate.net/publication/13853244_Long_Short-term_Memory

