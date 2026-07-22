# Course-1-Data-Analytics-for-Business
Data Analysis of Intenational Supermaket Chain, 2Market | Excel, Tableau, SQL (Postgres)

<b>March 2025</b>
Grade: 81% (Distinction)

## 2Market Marketing and Ad Data Analysis

### Context
2Market is a global supermarket that sells a range of products online and in-store. Previous years data will inform key business decision makers (CFO) as to how best to strategise forthcoming marketing campaigns. 2Market needs to maximise revenue as a key facet in profit maximisation, also contributing significantly to commercial targets; growth, share value, employee retention and more. It is important for 2Market to corroborate data across its seven locations to inform what works within its marketing strategy - to thus grow where it has lesser market share (Montenegro) and maintain the larger (Spain).

Whilst statistically significant causation has not been identified - the analysis explores trends, asking questions and providing recommendations of customers spending profile, acquisition route and purchasing behaviour. 

### Analytical Approach

With no data regarding marketing costs, the focus will be on revenue maximisation.

Firstly, data was transformed to create additional fields ‘Age of Customer’ and ‘Total Revenue’. Then, data was cleaned, applying both statistical methods (interquartile range) and logic to exclude nine observations deemed as outliers (Appendix A). Notable exclusions that applied statistical methods include ‘Age of Customer’ and  ‘Total Revenue’ whereby the upper limits of both were 82 y/o and $118k respectively (Appendix B/C). For Age, one exclusion was made where the observation had an Age of 121 - when the oldest person in South Africa in 2015 was 116 (BBC News, 2015). As for income, an observation posted an income of $666,666 - also assumed as a false data input.

Not all observations above the upper limits were excluded. Customers with the ages 114 and 115 were deemed feasible enough to be part of a true 2Market customer base, as were customers with incomes between $153k and $163k - as we may still be able to draw valuable conclusions from their behaviour. 

Another important exclusion is the removal of Montenegro. Having only three observations, analysis will not carry statistical weight to reflect the different socio-economic and behaviour of being a 2Market customer in Montenegro. Instead, it may skew analysis.

Appendix A provides a complete breakdown of data cleaning. Basic descriptive analysis was then performed to gather early understanding of the data set. 


<img width="250" alt="figa 2 market" src="https://github.com/user-attachments/assets/05b18c3e-9c14-4d17-a045-05290410b3fb" />

The highest frequency of customers fall in the $30k to $45k income bin.

<img width="250"  alt="figb 2market" src="https://github.com/user-attachments/assets/04e6d926-f66a-4aa5-8717-52d4366a4990" />

‘Widow’ has the highest mean Income of all Marital Status, ‘Single’ the lowest. 

The descriptive analysis assisted in the decision to be selective and generally disregard ‘Qualification’ and ‘Marital Status’ for the forthcoming analysis. As the dashboard has the end goal of identifying,’how’ and ‘who’ 2Market should target their marketing, location, age, income and what customers buy, are more important to a shop such as 2Market that sells ‘essential’ goods such as food.

INSERT CODE COPY

Finally, with PostgresSQL, Return on Conversion (ROC) was created to indicate the total income value of each conversion by country - allowing a quick way to evaluate where conversions are most effective in driving revenue - valuable for transferring learnings across marketing campaigns.

The 2Market Tableau worksheet has been designed to provide increasingly pinpointed analysis that answers core questions with each dashboard, leading to recommendations for 2Markets forthcoming marketing campaign. 

<img width="965" height="776" alt="figc 2market" src="https://github.com/user-attachments/assets/af72d418-2cc0-488d-ab52-b62917dbe2e2" />

The design is primarily for Desktop users and not yet optimised for mobile. The dashboards utilise two tone backgrounds to reduce visual overload, whilst ‘Key Points’ are emphasised with a navy blue box to allow users quick takeaways and visualisations use a bright colour pallet to assist in clear identification of trends. Filters also use this colour pallet and are positioned alongside the visualisations that they are referring to. Where possible, the F-Pattern is used to allow users to easily scan data. 

Each dashboard is titled and has 1-3 core questions that each dashboard answers. All the dashboards utilise live data directly from the ‘marketing_data’ and ‘ad_data’ CSV’s, bar ‘Customer Acquisition B’ that utilises data from the SQL built table ‘Return_On_Conversion’. Dashboard names are also grouped by tag colours and filters lay in line with the visualisations they are filtering, to assist in the flow of use and storytelling. 

‘Descriptive Statistics’ is less specifically directed at the 2Market CFO, however provides scoping for the three important metrics: Age, Income and Total Spending. 
For each of the non descriptive dashboards, the core focus metric changes: 

	Customer Spending Profile - Total Spent
	Customer Acquisition A - Count of Channel Acquisition
	Customer Acquisition B - Return on Conversion (SQL)
	Customer Location - Avg. Num. Shopping Type

A variety of visualisation types have been chosen, each to extract the most value from sets of relationships. Whatsmore, visualisations are strategically placed alongside one another to exhibit complementary or contrasting relationships. This is the case on ‘Customer Spending Profile’ where the placement of two scatter graphs measuring the relationship of ‘Customer Spending’ allow for cross comparison. This is also the case on ‘Customer Location’ where the same map is used to visually exhibit the difference in regional spending habits.

## Dashboard Design & Development

Firstly, Spain is the most valuable country, with over 6x the revenue value of Germany, India and the US individually. So any actions taken should help preserve this value or help to grow the value of the other countries.

The first recommendation regards the positive, gradual, linear relationship and exponential relationship between ‘Customer Spending’ and ‘Age of Customer’ and ‘Customer Income’ respectively. 2Market should target their marketing campaigns at older, wealthier individuals, regardless of country.

2Markets could maximise revenue by targeting their most valuable age group, 40-50. Age has an inverted U shaped relationship to Total Spend, reflective of the 2Markets Age Distribution in ‘Descriptive Statistics’. Interestingly, both age and country maintain similar levels of proportionate product spend. Meaning we cannot recommend targeting an age group, or country, with a particular product. The only exception is India - which spends proportionally, slightly less on Liquor.

Instagram drives the most revenue and Twitter drives the most deals and consistently converts the most across most countries. Customers aged 40-50, and with an income of $75k- have the highest count of responses to ads, with Instagram being the most popular within these age groups. An impactful insight would be to change the content of Twitter marketing to match Instagram, to drive higher value conversions.

Germany has the highest ROC (£208), the lowest India ($122). Considering Germany is 1/6th the value of Spain, more emphasis could be placed in driving conversions in Germany. Germany's highest channel was Twitter and bought mostly liquor. We suggest transferring marketing content from German Twitter to other countries.

With that, Germany had the biggest disparity between walk in and online purchases, favoring the former. So marketing could encourage customers to shop in stores more.

Interesting further investigation would include investigating family spending via ‘Child at Home’ and tailoring marketing to families.
