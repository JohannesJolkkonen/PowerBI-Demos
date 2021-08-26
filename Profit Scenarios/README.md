<h1 align="center">Power BI - Profit Scenario Planning</h1>


<p align="center">
    <img width="872" height="528" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Profit%20Scenarios/images/main.PNG>
</p>

## Overview

This model combines data from product costs, prices and sales volumes to visualize how changes to each of these variables impact profits.

Users have two sliders with which they can create scenarios with lower/higher sales volume or lower/higher manufacturing costs. 

##
<p align="center">
    <img width="594" height="360" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Profit%20Scenarios/images/tooltip.PNG>
</p>

## Feature Highlights

- Visual tooltips based on another report page, showing additional details when hovering over a visual. This is shown in the above image.

- Slider-ranges were created with GENERATESERIES(), and subsequent measures were based on the value(s) that users select by using SELECTEDVALUE(). This way, projections are dynamically re-calculated as soon as the slider value (=SELECTEDVALUE) changes. Meanwhile, baseline measures are held constant by using ALLSELECTED.

```DAX
Cost Change = GENERATESERIES(-0.2, 0.2, 0.01)
% Cost Change = SELECTEDVALUE('Cost Change'[Cost Change], 0)

Scenario Cost = 
SUMX( Sales,
	( Sales[Order Quantity] * ( 1 + [% Demand Change] )
		* Sales[Total Unit Cost] * ( 1 + [% Cost Change] ) ) 
    )
```

## Data

Dataset is a fictional one of ~1500 rows, created by IBM and found on [Kaggle](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset). 
Some small, cosmetic adjustments were made to the data towards the end, such as renaming Job Titles and Office locations. 

## Further Development 

 
