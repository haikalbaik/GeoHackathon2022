# GeoHackathon2022

## Problem Statement 

To predict and pick top formation given log data. The log data given varies in density, representing real world problem where not all logs are available for analysis.

## Methodology

### Checking data Coverage

As not all logs are present at all times, it is imperative to check which logs are available and can be used for prediction. 

![image](https://user-images.githubusercontent.com/47693704/204948301-65f347c9-7701-437f-b63d-6452b906bbc0.png)

### Log Viewer
The logs are viewed using [Cegal Tools](https://github.com/cegaldev/cegaltools). Simply do `!pip install cegal-welltools`

![image](https://user-images.githubusercontent.com/47693704/204949203-b27c20de-881d-49d6-ba53-ca4acd4f8553.png)


![image](https://user-images.githubusercontent.com/47693704/204949238-8753c5a0-0abd-4b53-a723-8aa21966515a.png)

### Dealing with Missing Data

For simplicty, all empty cells are filled with -999.25, we also will only use logs which covers 50% of wells. 

There are other methods such as deriving pseudo logs, feature engineering or statistical analysis for these missing data. 

## Results 

For simplicity, we are going to choose Random Forest Classification Algorithm with the following hyperparameters:

RandomForestClassifier(
n_estimators = 300, 
random_state=1,
max_features=12, 
max_depth=7, 
min_samples_leaf = 15)

This yielded 

![image](https://user-images.githubusercontent.com/47693704/204950966-24d29f83-486b-48c6-b26c-ef7212bd0cb9.png)

## Future Work

As this is only first pass of creating proper model, there are a lot more work that can be done in order to improve model accuracy. 

Mentioned earlier are methods such as psuedo logs, feature engineering or statistical analysis. 

We can also check data distribution, upscaling or downscaling so no oversampling for each formation. 

Investigating other models and searching for best hyperparameters using GridSearch or RandomSearch could also potentially improve model accuracy. 

Finally, potential work using lithology-based image as input can also be done to improve formation prediction that can tie with logs and lithology. 
