# signal-G-22prj

### Georgia 12-Lead ECG Challenge Database Analysis
## Introduction
in this project we'll use deep learning to apply classification to the data we got, the Georgia 12-Lead ECG database . This training set contains 10,344 12-lead ECGs (male: 5,551, female: 4,793) of 10-second length with a sampling frequency of 500 Hz.

this dataset has 122 different disease or heartbeat disorders

you can download the dataset from here
## preprocessing
since we have too many diseases , so we should concentrate on some of this diseases so first of all we looked through the .mat files which have the actual data and we found that almost all the data have a length of 5000 and only few records have length of 2500 so we've neglected the 2500 records

then we explored the.hea files and found that every disease has a special code or number so we've sorted the diseases and saw which are the most repeated disease so we choose the normal(sinus rhythm) and other five abnormal conditions

then we've labled all the normal with [0] and any other index or disease with [1] and then sheffled the list

finally , we apllied normalization to the data [fit transform] so we can deal with it

then the data was ready to be splitted into training and testing data and aplly the model

## LSTM Model
The first LSTM layer has 50 units (neurons) and expects input sequences with the shape (X_train.shape[1], X_train.shape[2]). X_train.shape[1] represents the number of time steps in each input sequence, and X_train.shape[2] represents the number of features in each time step.
return_sequences=True indicates that this LSTM layer returns the full sequence of outputs for each input sequence, which is necessary when stacking LSTM layers.
The second LSTM layer is similar to the first one but without return_sequences=True, as it only needs to return the final output.

![image](https://github.com/v23ymoezz/signal-G-22prj/assets/169824542/a502050a-5432-48d4-bf45-d100714d11a7)

## Result
# concusion matrix 
![image](https://github.com/v23ymoezz/signal-G-22prj/assets/169824542/2fae3fb3-959d-400f-b6fe-35f251bfa1c5)
# ROC curve 
 ![image](https://github.com/v23ymoezz/signal-G-22prj/assets/169824542/f54fbf15-02da-4f04-a55b-0462895cadb6)



