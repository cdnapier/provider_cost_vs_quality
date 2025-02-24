# Hospital Costs vs Quality of Care

## Table of Contents
* [Motivation](#Motivation)   
* [Data Question](#Data-Question)
* [Technologies Used](#Technologies-Used)
* [Challenges and Limitations](#Challenges-and-Limitations)
* [Data Sources](#Data-Sources)
* [Conclusions](#Conclusions)

## Motivation
I currently work in a health insurance brokerage space, where I help consult a variety of employers on the costs of their health insurance plans, and also act as a go-between between them and their respective insurance providers. In this line of work, I have had exposure to many different health tech companies and insurance vendors.  Some of them specialize in developing provider recommendation tools, which identify higher quality health providers within a given area based on many different types of metrics.  <br>
<br>
Currently, there is a surprising lack of transparency when it comes to selecting a healthcare provider for the average consumer, in terms of the costs they should expect to incur for a particular service, and the overall quality of care they would be receiving from said providers.  These recommendation tools allow customers to make more informed decisions when choosing doctors and facilities for care, and I was very interested in attemping to build one for myself.


## Data Questions
1) Does spending more for a particular medical procedure guarantee a higher quality of care from that provider?
2) Can we develop a basic hospital recommendation map to help steer consumers to higher-quality facilities in a given area?

## Technologies Used
* Python: For intial exploration, cleaning, and merging of the datasets.  Also used for geocoding the hospital address data (ie: assigning longitude and latitude values to each facility), made use of the geopy package for this process.
* Tableau: For visualizations and interactive dashboards, the hospital recommendation map is located in this file.


