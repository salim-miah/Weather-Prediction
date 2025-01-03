# Weather Type Prediction

## Table of contents
* [Introduction](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#introduction)
* [Data Description](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#data-description)  
* [Dataset pre-processing](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#dataset-pre-processing)
* [Feature Scaling](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#feature-scaling)
* [Dataset Splitting](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#dataset-splitting)
* [Model Training and Testing](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#model-training-and-testing)
* [Conclusion](https://github.com/salim-miah/Weather-Prediction/edit/main/README.md#conclusion)

## Introduction

Countless times it has happened that we needed to cancel a plan only
because of unexpected weather conditions. In a world where weather
impacts nearly every aspect of our lives, from travel plans to agriculture,
accurate and accessible weather prediction is crucial. This project aims to
classify weather conditions—Rainy, Cloudy, Sunny, or Snowy—based on
key environmental factors like temperature, humidity, wind speed, and
more. The problem it addresses is the need for accessible, localized, and
real-time weather predictions to help people make informed decisions.
Traditional weather forecasting methods can be resource-intensive, while
this AI-driven approach is both efficient and scalable. Doing this project was
fun because we could use AI to fairly accurately predict weather which is
otherwise a very complex thing to achieve.

## Data Description

### Source of the dataset:
[Dataset](https://drive.google.com/file/d/1ie1ExX44uqfCcan2B1MQdZ-Hcq5wLlQU/view?usp=drive_link)

### Description:
This Dataset has 10 features which are Temperature (quantitative), Wind
Speed (quantitative) , Precipitation (quantitative), Humidity (quantitative),
Cloud Cover (categorical), Atmospheric pressure (quantitative) , UV index
(quantitative), Season (categorical), Visibility (quantitative), Location
(categorical). These features will be used to predict the target variable
which is The Weather type. This is a classification problem because the
target variable is categorical and has 4 classes - Rainy, Cloudy, Sunny,
snowy. There are 13200 data points in the dataset initially.

### Correlation of all the features:
![image](https://github.com/user-attachments/assets/1fc43fb2-bfb7-42d4-b5c0-983dabf40662)

As we can see in the heatmap, the features are not very much correlated
with each other so every feature is very important for the model to correctly
predict the weather type.

### Balanced Dataset:
![image](https://github.com/user-attachments/assets/b6238215-dba4-4c9f-b91b-adc2d5f6614c)

As we can see, the number of instances of unique classes for the output
feature is equal. So it is balanced.

## Dataset pre-processing

First issue we faced is that there were some NULL values in the place of
some features in the dataset. For humidity, wind speed and precipitation, in
case of NULL values we simply imputed average values as there were only
1 case of NULL values for each. However, for temperature, atmospheric
pressure and Season it we decided to remove those data points because
there were more NULL values for each of them therefore imputing too
many average values may increase the inaccuracy of the model. Moreover,
Season is a categorical variable having separate classes, it will be
impractical to get an average value for it. As there are so many data points,
removing some rows should not be much of an issue overall.

The Second issue that we faced is there were many categorical variables in
our dataset. In order to work with the models, we need all features to be
numerical. Therefore we encoded those categorical variables. We used
One Hot encoding for season and location because we did not want the
models to imply any kind of ranking in those values as they are separate
classes of their own. We used label encoding for the cloud cover feature
because there was some sort of ranking in that data and we wanted the
model to recognize that. Finally we encoded our target value- Weather type
using label encoding as that was giving us more accuracy than one hot
encoding.

## Feature Scaling

Since some of the models can be affected while learning the data where
the value of features have drastic differences, scaler comes in handy to
tackle the issue and ensure that each feature (continuous variable)
contributes equally to the analysis. In the case of KNN model, we used
minmaxscaler as KNN is sensitive to the scale of input data. On the other
hand, features are scaled using standardscaler when using the Gaussian
Naive Bayes model as it assumes the feature to be normally distributed. In
the case of the Decision Tree model, feature scaling is not needed as it is
not sensitive to the scale of the data nor the distribution of the data.

## Dataset Splitting

We splitted the dataset into 2 parts.
70 % for Training.
30% for Testing.

We used stratified splitting so that after splitting the frequency of classes
remains the same which can improve the accuracy of the model.

## Model Training and Testing

We used 3 different models for the project.

* KNN
* Decision Tree
* Naive Bayes

## Model Selection/Comparison Analysis
![image](https://github.com/user-attachments/assets/01b2b59d-9ec5-438d-b560-6343530f9271)

As we can see, the Decision Tree Model has the most accuracy so it is the
most suitable model for this problem.

### KNN
#### Confusion Matrix and Classification Report:
![image](https://github.com/user-attachments/assets/bf4e71f9-7788-4b53-bb07-a27ba172f25f)

### Decision Tree
#### Confusion Matrix and Classification Report:
![image](https://github.com/user-attachments/assets/5790aace-1ff5-4441-a1c7-eaf86e3c8e28)

### Naive Bayes
#### Confusion Matrix and Classification Report:
![image](https://github.com/user-attachments/assets/516df968-7053-4c4b-94f4-99c0eb3fe0af)

## Conclusion

The Decision Tree Model is the most suitable model for classifying weather
conditions based on features such as temperature, humidity, wind speed,
and more because it has the highest accuracy. This AI driven approach is
efficient and scalable in contrast to traditional forecasting methods, which
can be exhaustive. The dataset was pre-processed by imputing average
values for missing data in humidity, wind speed, and precipitation. Data
points with missing values for temperature, atmospheric pressure, and
season were removed because they had a significant amount of missing
values. Categorical variables were encoded using one-hot encoding for
season and location, label encoding for cloud cover, and label encoding for
the target variable, weather type.

The dataset was split into 70% for training and 30% for testing using
stratified splitting to ensure the frequency of classes remained the same.
Three models were used: KNN, Decision Tree, and Naive Bayes . Feature
scaling was applied using min-max scaling for KNN and standard scaling
for Gaussian Naive Bayes. Feature scaling was not needed for the
Decision Tree model.

The project successfully classified weather conditions into Rainy, Cloudy,
Sunny, or Snowy. This project highlights the potential of AI in weather
prediction, making it a valuable tool for individuals and organisations
seeking accurate and localized weather information.

## Authors
- [Salim Miah](https://github.com/salim-miah)
- [MD Shohbat Ahsan](https://github.com/ShohbatPranto)






