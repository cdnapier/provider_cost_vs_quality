# Hospital Costs vs Quality of Care

## Table of Contents
* [Motivation](#Motivation)   
* [Data Question](#Data-Question)
* [Data Sources](#Data-Sources)
* [Technologies Used](#Technologies-Used)
* [Challenges and Limitations](#Challenges-and-Limitations)
* [Conclusions](#Conclusions)

## Motivation
I currently work in a health insurance brokerage space, where I help consult a variety of employers on the costs of their health insurance plans, and also act as a go-between between them and their respective insurance providers. In this line of work, I have had exposure to many different health tech companies and insurance vendors.  Some of them specialize in developing provider recommendation tools, which identify higher quality health providers within a given area based on many different types of metrics.  <br>
<br>
Currently, there is a surprising lack of transparency when it comes to selecting a healthcare provider for the average consumer, in terms of the costs they should expect to incur for a particular service, and the overall quality of care they would be receiving from said providers.  These recommendation tools allow customers to make more informed decisions when choosing doctors and facilities for care, and I was very interested in attemping to build one for myself.


## Data Questions
1) Does spending more for a particular medical procedure guarantee a higher quality of care from that provider?
2) Can we develop a basic hospital recommendation map to help steer consumers to higher-quality facilities in a given area?

## Data Sources
Hospital General Information and Star Ratings:<br>
https://data.cms.gov/provider-data/dataset/xubh-q36u

Medicare Spending Per Beneficiary:<br>
https://data.cms.gov/provider-data/dataset/rrqw-56er

Complication and Mortality Rates by Hospital:<br>
https://data.cms.gov/provider-data/dataset/ynj2-r877

Readmission Rates by Hospital:<br>
https://data.cms.gov/provider-data/dataset/9n3s-kdb3

Payment and Value of Care:<br>
https://data.cms.gov/provider-data/dataset/c7us-v4mf


## Technologies Used
* **Python**: For intial exploration, cleaning, and merging of the datasets.  Also used for geocoding the hospital address data (ie: assigning longitude and latitude values to each facility), made use of the geopy package for this process.
* **Tableau**: For visualizations and interactive dashboards, the hospital recommendation map is located in this file.

## Challenges and Limitations
* The datasets contain average cost data for only 4 types of medical conditions: Heart Attack, Heart Failure, Hip/Knee Replacement, and Pneumonia.  It would have been ideal to have more conditions to observe correlations for, preferably those with longer episodes of care (like Hip/Knee Replacement).
* Many hospitals in the dataset are either too small to report on cost/quality data, or just do not participate in the Medicare quality rating program entirely.  These null records were omitted from the map.
* In order to plot points on the map, the hospital addresses required geocoding within Python to obtain coordinate values.  Some hospitals could not be located with the geocoding method (roughly 1,000 out of 18,000 total records).  These specific facilities may appear within the hospital table in Tableau, but not on the map itself.

## Conclusions
Based on the correlations observed, at a minimum, there appears to be **little-to-no** correlation present between cost and quality of care.  This is the case for 3 out of the 4 types of procedures, but interestingly, for Hip/Knee Replacement, there appears to be a clear positive correlation, with higher costs being attributed to higher complication/mortality rates.  The reason for this is that the average per-patient costs in the dataset don't just represent the costs of the actual procedure, they represent the costs associated with the **entire episode of care**.  This includes additional follow up costs as a result of complications, readmissions, and potential revision surgeries.  And compared to the other 3 procedures (Heart Attack, Heart Failure, and Pneumonia), which are all rather episodic in nature, Hip/Knee Replacement has a relatively longer lifecycle of care, being a surgical procedure with a greater potential for follow-up care and perhaps readmission in some cases. 

As such, I believe the implication here is that higher quality facilities (ie: those with lower complication and readmission rates) tend to see lower than average costs, specifically when you observe per-patient costs over a longer period of time.  In other words, these are facilities that are highly efficient in what they do, delivering top quality care without complication or a need for significant follow-up care, resulting in lower average costs per patient overall.  These are providers that consumers should be driven to, and I believe that these types of recommendation tools should be an industry standard across health insurance companies.





