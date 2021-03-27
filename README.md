# ih_project_m3

Ironhack Madrid - Data Analytics Part Time - November 2020 - Project Module 3

<p align="center">
  <img src="https://camo.githubusercontent.com/fc370d9811c3bf7ac72595d0af0aa53c0d7b1ac4db2cffe1193f1590014cda60/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f3138342f312a3247446361655949785f6251415a4c78574d345073514032782e706e67">
</p>

### About
Given a diamonds dataset, from Kaggle, predict the prices of diamonds based on it's characteristics
You can found the competition [here](https://www.kaggle.com/c/dapt202011mad) 


### :information_source: datasource
1. A database provided by Kaggle and Ironhack


### :computer: **Technology stack**
Python, Pandas and SkLearn

#### For visualization:
Seaborn and Matplotlib

### :wrench: Configuration
Install Python 3.7 and pandas, seaborn, matplotlib and SkLearn lybraries.


### :file_folder: Folder structure
```
└── ih_project_m3
    ├── data
    │   ├── diamonds_train.csv
    │   ├── diamonds.csv
    ├── images
    ├── .gitignore
    ├── README.md
    ├── .ipynb
    
```

### :file_folder: Folder structure
There are two files provided by Ironhack:
1. Diamonds dataset (called train), with all the features and the price of more than 40000 diamonds.
2. Diamonds dataset (called test), with all the features + and ID column. This dataset does not contain the price and is used to determinate our RMSE at the competition.
3. Submission csv. CSV(s) with the predictions of our model(s)


### :file_folder: Steps
First of all, we analyze the info, get ride of null values and outliers.
With the dataset clean, we need to enconde the categories columns and create some new ones with the info we have.
We've created the following columns:
    Volume
    Length and width ratio
    Logaritmic carat

The first two columns uses dimensions info, so we can drop x, y, z from our dataset. The last one was created 'cause carat has a strong relation with the price and this relation it's exponential, not linear.

Once we have the dataset clean and all the columns we gonna need prepared, we have to encoded the categorical ones, 'cause the ML models needs numbers to learn. We choose label enconding, 'cause it has better results than OneHotEncoding.

Finally we got to the funny part, we've tried 5 differents models:
    Random Forest Regressor
    Decision Tree Regressor
    Gradient Boosting Regressor
    HistGradientRegressor
    Extra Tree Regressor

We found out that best results comes from Gradient Boosting and HistGradientBoosting. The metrics we used are:
    MAE
    RMSE
    R2
    Cross validation