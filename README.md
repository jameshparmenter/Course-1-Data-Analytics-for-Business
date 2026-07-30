## Course 1: Data Analysis for Business

In 'Data Analysis for Business', we were provided with the foundational tools to inform business decisions. These tools include using <b>Excel</b> to run descriptive statistics, data transformation, plus using <b>Tableau</b> to create insightful, interactive dashboards. Finally we acquired the <b>foundational SQL</b> to complete JOINs, QUERYs and to retrieve data. In this course, we also learned effective <b>stakeholder engagement</b>, and how to <b>define the business problem</b>.

Please find the <a href='https://github.com/jameshparmenter/Course-1-Data-Analytics-for-Business/blob/main/Parmenter_James_DA301_Assignment_Report.pdf%20%20(1).pdf'> full report above.</a>

<b>Grade: 86% </b>

## The Assignment:

For the assignment, we were provided with the data of a hypothetical supermarket chain ‘2Market’ that is seeking to plan marketing spend and strategy.

## Building Context

First, it was necessary to define the business problem and who the report is directed towards: 

<i>‘Previous years data will inform key business decision makers (CFO) as to how best to strategise forthcoming marketing campaigns. 2Market needs to maximise revenue as a key facet in profit maximisation, also contributing significantly to commercial targets; growth, share value, employee retention and more’</i>


## Analytical Approach

The data was medium in size, consisting of two datasets containing 2156 observations and 29 total variables. The following statistical and logical steps were completed to transform the raw dataset into one ready for analysis: 
<ul>
  <li>Identify and Remove Duplicate Observations</li>
  <li>Identify and Transform Missing Values</li>
  <li>Create new variables for Analysis (Age of Customer’ and ‘Total Revenue’)</li>
  <li>Perform Outlier Analysis on Core Values - dropping observations where necessary</li>
</ul>
<i>‘As for income, an observation posted an income of $666,666 - also assumed as a false data input.’</i><br>
<i>‘Not all observations above the upper limits were excluded. Customers with the ages 114 and 115 were deemed feasible enough to be part of a true 2Market customer base’</i><br>

With the dataset made appropriate for analysis, we used Excel to run further descriptive statistics to gain insights into the shape and spread of the data. Here, we found the frequency of customers per income bin - and decided to disregard ‘Qualification’ and ‘Marital Status’ from further analysis as they were less significant indicators as to ‘how’ and ‘who’ 2Market should target in the marketing campaign. 

In PostgresSQL we created a unique metric of Return on Conversion - to indicate the total income value of each conversion, allowing us to filter this by country, age etc in our analysis:

`ROC = Total Country Income / SUM(Count of Twitter, Instagram, Facebook, Brochure, Bulkmail)


## Dashboard Design & Development

For dashboard design and development, I found praise for building a story-telling dashboard that applied increasingly pinpointed analysis, targeted at the business problem.

The flow of the dashboard was as follows:
<ul>
<li>Descriptive Analysis: ‘What is the make-up of the dataset?’</li>
  <li>Spending Profiles: ‘Who should 2Market target?’ ‘Which products should they target’</li>
  <li>Acquisition Channels (A): ‘What Channels should 2Market target?’ ‘Where and what customer profile?’</li>
  <li>Acquisition Channels (B): ‘What can we learn from the countries with the highest ROC?</li>
  <li>Customer Location with Key Points Summary: ‘How should 2Market adapt marketing to customer shopping habits?’</li>
</ul>


<img width="807" height="650" alt="2market5" src="https://github.com/user-attachments/assets/f43559f7-4c75-493c-846c-d5588185427c" />
<img width="3696" height="1425" alt="2market34" src="https://github.com/user-attachments/assets/836593bd-793d-46c0-8b94-5b6991e07c60" />
<img width="3590" height="1409" alt="2Market12" src="https://github.com/user-attachments/assets/55259186-f1c5-4fcb-8e9a-1c0e0314124c" />

## Patterns Trends & Insights
Our structure was to answer a core question on each dashboard, culminating in a connected story.
<i>‘Spain is the most valuable country’</i>
<i>‘2Market should target their marketing campaigns at older, wealthier individuals, regardless of country’</i>
<i>‘...we cannot recommend targeting an age group, or country, with a particular product. The only exception is India - which spends proportionally, slightly less on Liquor.’</i>
<i>‘An impactful insight would be to change the content of Twitter marketing to match Instagram, to drive higher value conversions.’</i>
<i>‘Germany has the highest ROC (£208), the lowest India ($122). Considering Germany is 1/6th the value of Spain, more emphasis could be placed in driving conversions in Germany.’</i>
<i>‘Interesting further investigation would include investigating family spending via ‘Child at Home’ and tailoring marketing to families.’</i>
