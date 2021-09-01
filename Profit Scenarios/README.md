<h1 align="center">Power BI - Profit Scenario Planning</h1>


<p align="center">
    <img width="872" height="528" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Profit%20Scenarios/images/main.PNG>
</p>

## Overview

This model combines data from product costs, prices and sales volumes to visualize how changes to each of these variables impact profits.

Users have two sliders with which they can create scenarios with lower/higher sales volume or lower/higher unit costs. 

The live model is available [**here**](https://app.powerbi.com/view?r=eyJrIjoiODYxYmZmNTAtNjhhNC00ZTc1LWE2OGQtNDIxNjc2MmFhNDJmIiwidCI6IjlkM2ViZWMyLTI3OWItNDY2NC05YmViLTU4YmEzNjI2MGVlMyIsImMiOjh9&pageName=ReportSection1d1273d39191e292b007)

##
<p align="center">
    <img width="594" height="360" src=https://github.com/JohannesJolkkonen/PowerBI-Demos/blob/master/Profit%20Scenarios/images/tooltip.PNG>
</p>

## Feature Highlights

- Visual tooltips based on another report page, showing additional details when hovering over a visual. This is shown in the above image.

- Slider-ranges were created with GENERATESERIES(), and subsequent measures were based on the value(s) that users select by using SELECTEDVALUE(). This way, projections are dynamically re-calculated as soon as the slider value (=SELECTEDVALUE) changes. Meanwhile, baseline measures are held constant by using ALLSELECTED.

```DAX
Demand Change = GENERATESERIES(-0.20, 0.21, 0.01) --Returns a single column table, which is used as the value for demand-slider
% Demand Change = SELECTEDVALUE('Demand Change'[Demand Change], 0) --Returns the currently selected value of the demand-slider

Cost Change = GENERATESERIES(-0.2, 0.2, 0.01) --Returns a single column table, which is used as the value for cost-slider
% Cost Change = SELECTEDVALUE('Cost Change'[Cost Change], 0) --Returns the currently selected value of the cost-slider

Scenario Cost = 
SUMX( Sales,
	( Sales[Order Quantity] * ( 1 + [% Demand Change] )
		* Sales[Total Unit Cost] * ( 1 + [% Cost Change] ) ) 
    )
```

## Data

The datasets used were randomly generated with Python, numpy and Mimesis. See https://github.com/JohannesJolkkonen/mock-business-data-generator.

## Development Notes

 
