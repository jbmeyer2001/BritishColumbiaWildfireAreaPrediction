# BritishColumbiaWildfireAreaPrediction
Intro/purpose:
The purpose of this project was (and is) to get more familiar with machine learning and working with real-world data (not necessarily nicely formed datasets given as part of an assignment). 
Using the data that I was able to find, both governmental sources, one being a record of wildfires in British Columbia and the other being yearly weather data from within different fire zones in BC, I
tried to create a machine learning model to predict the area of wildfires in a given fire zone on a certain month.

Data collection/formatting:
The first challenge of this project was acquiring and formatting/preprocessing the data. The data that I was able to find limited what I was able to do. For example, if I was able to find historical weather
data for many individual points across BC, alongside wildfire data on the same points, and possibly even satellite images from those points I would have liked to do some kind of survival analysis to
calculate the churn rate of different areas across the province. However, while I was able to find geographical data for the fires, I was not able to find it for the weather (which is understandable considering
there aren't weather stations all over the less populated parts of the province), and even if I had the project likely ballooned into something unfeasible for a personal project. The way that I overcame
this was by simplifying the project - attempting to predict the area of wildfires that will burn in a given fire zone utilizing time series analysis. The data was formatted to predict the area (in hectares) 
that will burn in a given fire zone in a given month, using both present and lagged features of temperature and precipitation.

Machine learning/data analysis:
The next challenge was in machine learning and data analysis. It became very clear that the data I was not able to account for the complexity of the problem, and thus the predictions were not meaningful.
I first started by trying to find which model I would select (between Linear Regression, Decision Tree Regression, SVM RBF (SVR), and LightGBM Regression). SVR was the clear front runner of the four,
although it was still very poor at predicting wildfire area, unfortunately since there was not enough representation of fires, the model would continuously predict very low values (often under 10 hectares)
for every month, even July and August in large fire zones. I streamlined the process for testing these four different models and tried a couple of things to give fires more representation in the data such as:
only training and testing different models on months where fires are most likely (June, July, August), switching to calculating the fires in a given year instead of a month. Unfortunately, despite this the
models were never able to overcome the prevalence of seasons/months without fires, to be able to predict when a bad year might occur. Indeed, these attempts to simplify the model only made the accuracy worse.

Takeaways:
Despite the fact that this project was a flop in its actual usefulness (something that I sort of expected), it was a very good learning experience for working with and parsing real-world data, and I was
able to improve my knowledge of the fundamentals of data analysis and machine learning.
