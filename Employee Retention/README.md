<h1 align="center">Power BI - Predicting Employee Flight Risk</h1>

<p align="center">
    <img width="872" height="528" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Employee%20Retention/images/flight-overview.PNG>
</p>

## Overview

This model was built using employee records, which were first enriched with an Azure Machine Learning model to predict a flight risk for each employee.

Using the Key Influencers -visual among others, employee segments can be identified for which the predicted likelihood of employees leaving are disproportionately high.

The model was inspired by BlueGranite's work [here](https://www.bluegranite.com/blog/power-bi-showcase-employee-retention-organizational-flight-risk), but nonetheless built from scratch and with unrelated data.

##
<p align="center">
    <img width="872" height="528" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Employee%20Retention/images/key-drivers.PNG>
</p>

## Feature Highlights

- A Decision Tree algorithm was implemented with Azure ML Studio for predicting flight risk

- Based on an average cost of losing and replacing employees, a simple estimate was made for annual, org-wide costs of employee flight

##
<p align="center">
    <img width="792" height="480" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Employee%20Retention/images/details.PNG>
</p>

## Data

Dataset is a fictional one of ~1500 rows, created by IBM and found on [Kaggle](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset). 
Some small, cosmetic adjustments were made to the data towards the end, such as renaming Job Titles and Office locations. 

## Further Development 

 
