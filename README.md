# Hasan_Sully_Hackathon
Hasan Zaidi Submission for the Sully Hackathon

Link to dashboard: https://lookerstudio.google.com/reporting/3b2f19dc-05eb-457a-9030-a38bd588ab68

Process

EDA
I started by loading the data. It needed some minor cleaning, that I did. Handled a few missing values, both agent and company had a large amount of rows as empty, but both those variables had no entries with 0, so I converted NA to 0. 

Similarly where children were missing I add a 0, that did seem like the right business decision as well. 

For any other minor number of rows with missing values, I dropped them. 

I then manually set the data type for each column. I did this step in the interest of making this script scalable for any future ETL activities using the same dat sources. 

Data Warehouse

I created a star schema and made tables from my data frame. 
I used Sqlite3 to create a local db

Dashboard

I used google looker for the dashboard. I uploaded the db tables as CSVs to looker and created the visualizations. 

ML

I wrote a simple logistic regression model to classify booking cancellations. I tried an adjusted threshold model and got some varying results. The final selection depends on the business outcome required. 
Where missing cancellations carry a higher cost , then adjusting the threshold (second model) to prioritize higher recall for cancellations may be the better choice
On the other hand, if business goal is to minimize false alarms and only flag cancellations when highly confident, sticking with the original model is better.

