F1 Lap Time Prediction using Linear Regression
Project Overview

This project predicts the lap time of an F1 car using Linear Regression.

I selected lap time because it is a continuous value, which makes it a better choice for Linear Regression than predicting finishing position. The main goal of this project was to understand the complete machine learning workflow, including data cleaning, feature engineering, model building, and model evaluation.

About the Dataset

I used the Formula 1 dataset from Kaggle. The following files were used in this project:

lap_times.csv – Contains lap time for every driver in every race.
races.csv – Contains race details such as year, round, and circuit.
results.csv – Used to identify the constructor (team) for each driver.
pit_stops.csv – Used to calculate the number of laps since the last pit stop.

The target variable is the lap time in milliseconds.

Data Preparation

Before building the model, I cleaned the data by removing very slow laps. These laps usually happen because of safety cars, accidents, or other race incidents and can affect the model performance.

Features Used

The following features were created for the model:

Lap Number – Current lap of the race.
Laps Since Pit Stop – Number of laps completed after the last pit stop.
Driver Form – Average performance of the driver in the previous races.
Constructor Form – Average performance of the team in previous races.
Circuit Baseline – Average lap time for that circuit based on previous races.

These features were created using only information that would have been available before that lap.

Model Building

The dataset was divided based on the race year.

Training Data: Up to 2021
Testing Data: 2022 onwards

The numerical features were scaled using StandardScaler before training the Linear Regression model.

Model Evaluation

The model was evaluated using the following metrics:

Mean Absolute Error (MAE)
Root Mean Squared Error (RMSE)
R² Score

The results were also compared with a simple baseline prediction to check whether the model performed better.

Limitations

This dataset does not contain some important information such as:

Tyre compound
Weather conditions

These factors have a big impact on lap time, so including them could improve the model in the future.

Future Improvements

Some improvements that can be made are:

Use a dataset that includes tyre and weather information.
Build separate models for different circuits.
Improve the handling of laps immediately after pit stops.
Project Files
01_eda.ipynb – Data exploration and analysis
02_feature_engineering.ipynb – Feature creation and data preparation
03_linear_regression_model.ipynb – Model training and evaluation

Run the notebooks in the following order:

01_eda.ipynb
02_feature_engineering.ipynb
03_linear_regression_model.ipynb
