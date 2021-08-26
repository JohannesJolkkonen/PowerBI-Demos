# Power BI Customer Acquisition Performance 

<p align="center">
    <img width="991" height="600" src=https://github.com/JohannesJolkkonen/powerbi-customer-acquisition/blob/main/images/tm-performance.PNG>
</p>

## Overview

This model combines data from softphone records and a CRM to monitor the performance of both pre-sales (telemarketing) and sales (account management). 

Key metrics include meetings arranged, calls made per meeting arranged, cancellation rate of meetings, and new customers for each employee. These can also be viewed as averages at the level of months or weeks.

The live model is available at []


## Feature Highlights
- Customers/Prospects typically have a relationship with more than one sales operator. For most DAX-measures, this relationship context needed to be managed with the use of USERELATIONSHIP-functions.

- Softphone features were used to filter between outbound calls, inbound calls, internal calls as well as calls that end with connection errors.

- Customer retention is calculated by comparing dates of their first and last transaction, and a long-term retention rate is subsequently calculated for all account managers, as a %-share of all their accounts.

- There were some inconsistent data formats and naming conventions between the Softphone and the CRM, which were fixed with Power Query.    

- Usage hints that can be shown and hidden with a click, created by using buttons and bookmarks

## Data

The datasets used were randomly generated with Python, numpy and Mimesis. See https://github.com/JohannesJolkkonen/mock-business-data-generator.

## Further Development 
