# Uber-Driver-Availability

uber is ride hailing company. many car or taxi driver are associated with uber. So, Whenever drivers are online, uber get pings from their mobile phone indicating that they are available for the ride. we have a uber drivers data and ping timestamp and we have to predict the online hrs availability of the drivers.

we have been provided with 3 weeks of training data and 1 week of test data.

What this data about?

The dataset has three files. The data in the first two files can be used for training the model and the third file contains test data.

drivers.csv: This file contains drivers profile data
pings.csv: This file contains: This file contains the drives pings
test.csv: This file has the test data
The fields present in these files are described below.

drivers.csv:

id: Unique driver id
gender: Gender of the driver
age: driver’s age
numberofkids: The number of kids the driver has

pings.csv:

id: The id of the driver whose ping has been received. It is guaranteed that the details of this driver will be available in the driver.csv file.
timestamp: The Unix epoch timestamp when ping was received by the system.

test.csv:

id: The id of the driver whose ping has been received. It is guaranteed that the details of this driver will be available in the drivers.csv file.
date: The date in YYYY-MM-DD format for which the online hours needs to be predicted.
onlinehours: The number of online hours Given id and date, you should predict onlinehours.

Approach to the problem:
1) Check for the null values in all 3 csv files.
2) convert unix timestamp into the online hours. here I have taken one step difference of the timestamp for each driverid and each date. if the difference is less than 2 minutes then the online hours are same but if the difference is more than 2 minutes then cap it to 2 minutes.
3) take sum of the differences for each driver and each date. you will get the online hours.
4) Data Visualization,Data Preprocessing, and Data Cleaning.
5) merge driver,ping, and test dataset based on drivers_id.
6) apply possible regression models on the merge dataset without any feature engineering.
7) create new features based on the date,rolling window mean and lag.
8) again train the model on new features.
9) find out the weight or the importance of the features and based on that keep few important features.
10) again train the model on final dataset.

I have used regression models for this problem. Due to lack of data and computational power I have not gone with the deep learning (LSTM models).
