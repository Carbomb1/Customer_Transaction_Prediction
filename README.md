# Santander Transaction Prediction

## Background
Banco Santander, S.A. is a multinational financial services company based in Spain. Santander wants to be able to identify which customers will make a specific transaction in the future, irrespective of the amount of money transacted. To help achieve this they sponsored a Kaggle competition. This repository holds my final code used tackle this competition. \
Kaggle competition link - https://www.kaggle.com/competitions/santander-customer-transaction-prediction/overview

## Main Strategies Used

### "Fake Data" in the testing dataset
In the testing dataset there is "Fake Data", this fake data is synthethic data that was created off of real data. The fake data features can be identified if none of the values in the features is unique. In the testing data set, half of the data is real data and half is synthetic data created from the real data. This fake data had led to poor performance when training the model. To solve this problem new features were created based on the frequency of each value that shows up in every column. This added 200 more features to the testing data. But because this data was not normalized 200 more features were added taht were scaled.


### Model Used for Final Predictions
My best performing model ended up being a LightGBM model. The optimal hyperparameter settings for this model were discovered using Bayesian Optimzaiton. To achieve the final predictions for the model, Stratified K-Fold was used due to a 10:90 class imbalance. The final predicted values were an average of the values of the K number of rounds. 


## Results
In my final results file I was able to achieve an AUC score of 0.91227. With the highest official score being 0.92573

![image](https://user-images.githubusercontent.com/45641348/168448844-069fb4be-4981-4ddc-94ec-2af5d0c497a4.png)

## Contents of Repository

### Code File
The Santander_Prediction_Code.ipynb file shows the detailed steps to arrive at the final predictions. The file was written using Python through a Google Colab notebook

### Submission File 
The Submission_File.csv contains the final predictions that were uploaded to the Kaggle competition. 

