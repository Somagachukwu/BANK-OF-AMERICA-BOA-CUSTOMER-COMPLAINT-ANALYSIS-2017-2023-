# BANK OF AMERICA (BOA) CUSTOMER COMPLAINT ANALYSIS (2017–2023)
![image.alt](https://github.com/Somagachukwu/BANK-OF-AMERICA-BOA-CUSTOMER-COMPLAINT-ANALYSIS-2017-2023-/blob/main/BOA/BOA.png)

# INTRODUCTION
#### Bank of America (BoA) is one of the largest financial institutions in the world, headquartered in Charlotte, North Carolina. Founded in 1904, it has grown into a leading global bank serving individual consumers, small and mid-sized businesses, and large corporations with a broad range of banking, investing, asset management, and other financial and risk management products. BoA is known for its extensive network, with thousands of branches and ATMs throughout the U.S., as well as a robust online and mobile banking platform that serves millions of users.

#### In today’s fast-paced and competitive financial business environment, customer satisfaction is important to help the business thrive. Customer complaints are an essential source of feedback, providing direct insight into areas where services, products, or processes may fall short of customer expectations.

#### This report presents an in-depth analysis of customer complaints from 2017–2023. The analysis aims to identify recurring issues, trends, and areas for improvement, and propose informed, data-driven recommendations that Bank of America (BoA) can implement to effectively address and reduce customer complaints.

#### This analysis not only highlights the most common types of complaints but also explores patterns across various customer segments, including product type, geographic region, issues, and timely response. The findings will support the company in prioritizing resources and implementing strategies that address the most critical pain points in customer journey.

## Problem Statement
#### Bank of America (BoA), a financial institution based in the United States, has received numerous customer complaints over the years. To address this, BoA has decided to analyze consumer complaints related to its financial products and services from 2017 to 2023.
#### BoA has put together a comprehensive dataset around rows, containing detailed information on each complaint, including submission and receipt dates, associated products and issues, and BoA’s responses. The following is expected from this analysis:

1. Detecting trends in complaint volume and types over the years.

2. Assessing the timeliness and adequacy to BoA’s responses to complaints

3. Highlight the common problems consumers face and evaluate BoA’s effectiveness in addressing these issues.

## Analysis Approach
#### Whilst the requirement has been spelt out, I inspected the dataset to see if the available data was enough to provide the needed solution.

## About the Dataset
#### The dataset contains an Excel workbook which contains 12 columns and about 60,000 rows
### The columns contains the following:
* Complaint ID: The unique Identification number for each complaint laid.
* Submitted via: The mode of submission of the complaint.
* Date Submitted: The date the customer submitted a complaint.
* Date Received: The date the institution received the complaint.
* State: The place where the customer resides or where they are making the complaint.
* Product: The product category for which the customer is complaining.
* Sub-product: The product under the product category for which the customer is making a complaint.
* Issue: The reason the customer is filing the complaint.
* Sub-issue: The category within the issue of filing the complaint.
* Company Public Response: Response given to the public about these complaints.
* Company Response to Consumer: Response given to the customers regarding the complaints.
* Timely Response: If the customers’ complaint was responded to within an appropriate timeframe.

## Methodology
### Data Manipulation

### Microsoft Excel and Power query were used to clean and manipulate this dataset. Why power query and excel? This is because it is easier to use and is more accessible, power query records each transformation step and it is also compatible with the visual tool Power BI.
### The dataset underwent some processes like removing duplicates, for columns like the company public response, sub-issue, sub-product, and timely response which had some blank rows. No response, not specified, N/A, and unknown were used to fill empty cells of each column respectively. Some might ask why I used unknown to fill in the empty cells in the timely response column. This was because when cleaning the data I filtered out the empty cells for the timely response and noticed that for every blank cell in that column, the company response to the consumer was still in progress. Xlookup function was used to bring in the full names of the states as they were written in abbreviation.

## Splitting Table into Facts and Dimensions Table
#### With that done, I inspected the dataset and decided to split the tables into fact and dimensions table as this would improve the performance and optimize the report development. The Customer complaints table was used as the fact table and I used some of the columns to create a dimension table by selecting the column I dimmed fit to use and removing other columns and then adding index columns. The columns used for the dimensions table are the product column, issue column, timely response column, sub-product column, and submitted via column.

## Creating a Date Table
#### I observed that I needed a date table because I would be working a lot with dates and time. It is a best practice in data analysis to have a dedicated date table when you have to perform time-intelligence analysis. I achieved this by using DAX (Data Analysis Expressions).

## Building the Data Model
#### While the fact, dimensions and date table have all been created, I closed Power Query and loaded my data ready to be modelled. I established relationships by connecting the primary keys on the dimensions table to the foreign keys on the facts table and this ended up in a Star Schema Data Model. Below is a pictorial representation of the data model:
![image.alt](https://github.com/Somagachukwu/BANK-OF-AMERICA-BOA-CUSTOMER-COMPLAINT-ANALYSIS-2017-2023-/blob/main/BOA/BOA%20Modelling.png)

## LIMITATIONS
- Missing Data
- Inconsistent Formatting
- Dataset was only limited to categorical data

## Analysis
#### After the modelling was done and all the necessary relationships established, the next stage is to start analyzing the data and creating a beautiful dashboard that would show all key metrics and actionable insights that can easily be understood even by non-technical personnel.The dashboard consisted of two pages.
#### The first Page displays a summary of the entire report featuring Key Metrics such as:
* Total No of Complaints: The count of all the complaint ID
* Product: The distinct count of the products provided by the financial institution and which complaints were laid on.
* Issue: The distinct count of the issues of the complaint.
* Submission Mode: The distinct count of the mode of submission of the complaints.
* State: The distinct count of states from which the complaints were laid.
* Percentage of Timely Response: The percentage total showing if the customers were responded to on time.
* Company Public Response: The number of each response to the public by the total number of complaints.
* Company Response to Consumer: The number of each response to the consumers by the total number of complaints
* Yearly Trend of Complaints: The total number of trends for each year.
* Timely Response by Submission Mode: The number of responses given based on how the complaint was submitted.
* Complaint by Product: The number of complaints given for each product.

![image.alt](https://github.com/Somagachukwu/BANK-OF-AMERICA-BOA-CUSTOMER-COMPLAINT-ANALYSIS-2017-2023-/blob/main/BOA/BOA%20pg%201.png)

## The second is a continuation of the key metrics, which include:
* Complaints by State: These show how many complaints were recorded for each state.
* Complaint by Months: The total number of complaints recorded by each month
* Complaint by Year and Month: The total number of complaints recorded in each month in the different years contained in the dataset.
* Submission mode: shows the total number of complaints recorded from each mode of submission.

![image.alt](https://github.com/Somagachukwu/BANK-OF-AMERICA-BOA-CUSTOMER-COMPLAINT-ANALYSIS-2017-2023-/blob/main/BOA/BOA%20pg2.png)
  

## Observation
#### The following are my observations from exploring the dataset:
1. Annually, July and May compete for the months withthe highest number of complaint records, recording a total number of 6,455 and 5,748 complaints respectively.
2. The month with the least number of complaints annually is February recording a total number of 4,510 complaints.
3. 2022 recorded the highest number of complaints with a record of 13,000 complaints and 2017 recorded the least with a total number of 5000 complaints.
4. Most of the complaints came from the product checkings or savings account which recorded about 25,000 complaints in total.
5. The company’s response to the customer shows that 41,000 customers were closed with an explanation and 15,000 closed with monetary relief.
6. The products pay day loan, title loan or personal loan and student loan recorded no number of complaints.
7. The percentage of timely responses varies from 93.77%, 3.84% and 2.39% for yes, no, and unknown respectively.
8. The mode of submission used more to file the complaints was the web and it also recorded the highest number of yes for the timely response.
9. California recorded the highest number of complaints with a total record of 13,709 while Wyoming and North Dakota recorded the least number of complaints with a record of 22 respectively.

## Recommendations
#### Based on the above observations, here are my humble recommendations.
1. Conduct a Root Cause Analysis on Frequent Issues: The company should use tools like the “5 Whys” or fishbone diagrams to dig deeper into why these problems occur.
2. Focus on the Most Common Complaint Types: Prioritize resolving the top complaint categories by implementing specific fixes.
3. Enhance Customer Service Training: Train customer service teams to handle complaints empathetically and effectively. Focus on active listening, problem-solving, and de-escalation techniques.
4. Monitor and Reduce Repeat Complaints: Establish a follow-up mechanism to check in with customers after resolving their complaints. Offer additional support to repeat complainers, such as a dedicated representative, and ensure their complaints are fully addressed.
5. Encourage Continuous Feedback and Improvement: After complaints are resolved, send follow-up surveys to assess customer satisfaction with the resolution process. Use this feedback to improve processes and establish a culture of continuous improvement. Consider implementing regular check-ins or feedback requests with customers to understand and address potential issues before they escalate into formal complaints.

## Conclusion

#### The analysis of BoA’s financial institution has provided valuable insights into the company’s activities, operations, and performance. The findings highlight areas of strength, such as the low complaints in products like student loan. However, the analysis also reveals opportunities for improvement such as optimizing and fixing in-depth problems of some of the products. These data also revealed that the institution cares about its customers as they were responded to swiftly.
#### By implementing the recommendations outlined in this report, the company can enhance revenue generation, boost productivity, and drive business growth.

# Thank you for reading!

