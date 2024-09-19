

**Adetutu B.**

**Data Acquisition SQL Task**

**A: Research Question**  
Are customers who experience more than 10 seconds of power outages a week more likely to experience yearly equipment failure within a year, and how does it correlate with how often they replace their devices?

**A1: Justifying the Question**  
Power outages have the ability to strain and damage devices which can cause device owners to lose important information and time trying to restore their data from a fixed or replaced device. My goal for this query is to gain insight on the possible relationship between outages longer than 10 seconds and yearly equipment failure for customers– and how it correlates with the frequency of device replacements. I will attempt to answer by only looking at customers who experience weekly outages for 10+ seconds and compare it to whether they replaced at least 1 device within a year.  Data containing how many times the customers of interest replaced their devices will also be included to check for a correlation between needing to replace devices and experiencing certain lengths of outages and annual equipment failure. Businesses can use these insights to create bundled device protection and online backup service deals for customers who have dealt with outages and equipment failure, or may deal with it in the future. If more information was available, figuring out possible seasons where this issue may be more prevalent to consumers could enable businesses to offer seasonal service deals to prevent– and appease– affected customers.

**A2: Data Identification**  
I will need 4 columns to answer my research question. From the customer table in the original churn database, I will be utilizing the “outage\_sec\_week” and “yearly\_equip\_faiure” columns. I will create an add-on table using the “Survey\_Responses.csv” file and need the “timely\_replacements” column to answer my question. The “customer\_id” from both the original database and the add-on CSV will be joined together to help identify each unique customer. While the unique identifier and all the needed variables are originally integer data types, I chose to alter the “yearly\_equip\_faiure” column to present as a VARCHAR data type to show that all zeros represented “No” (the customer did not experience equipment failure) and “Yes” (the customer did experience equipment failure).

**B: Database ERD**  
![][image1]

**B1: Describing the Relationship**  
In order to include the survey responses from the add-on CSV I created a table for it to be included with the other tables in the original database. For my query I used columns from the customer table and survey\_responses table. I made the customer\_id column a primary key so each individual customer could be uniquely identified. However, I also made customer\_id a foreign key so the relationship between the customer table and survey\_responses were linked and being added to one table required addition of the necessary information in the other table as well.

**B2: Add-on CSV Table**  
\--Create Add-On Table for survey data  
CREATE TABLE public.Survey\_Responses  
(  
     customer\_id TEXT NOT NULL,  
     Timely\_Responses INT NOT NULL,  
     Timely\_Fixes INT NOT NULL,  
     Timely\_Replacements INT NOT NULL,  
     Reliability INT NOT NULL,  
     Options INT NOT NULL,  
     Respectful\_Responses INT NOT NULL,  
     Courteous\_Exchange INT NOT NULL,  
     Active\_Listening INT NOT NULL,  
     PRIMARY KEY (customer\_id),  
     CONSTRAINT fkey\_id  
          FOREIGN KEY (customer\_id)  
               REFERENCES public.customer (customer\_id)  
);

ALTER TABLE public.Survey\_Responses  
     OWNER TO postgres;

**B3: SQL Loads CSV Data**  
\--Loading survey.csv data  
Copy Survey\_Responses  
FROM 'C:\\LabFiles\\Survey\_Responses.csv'  
Delimiter ','  
CSV HEADER;

**C: SQL Query Statement**  
\--SQL Query  
ALTER TABLE public.customer  
ADD yrly\_equip\_failure VARCHAR;

UPDATE public.customer  
SET yrly\_equip\_failure \=  
(CASE  
     WHEN yearly\_equip\_faiure \>='1' THEN 'Yes'  
     ELSE 'No'  
END  
);

SELECT cu.customer\_id, cu.outage\_sec\_week, cu.yrly\_equip\_failure, su.timely\_replacements  
FROM customer cu  
LEFT JOIN public.Survey\_Responses su on cu.customer\_id=su.customer\_id  
WHERE cu.outage\_sec\_week \>=10  
ORDER BY cu.outage\_sec\_week;

**C1: Query Results**  
My query results have been included as a separate CSV file.

**D: Add-on File Refresh Period**   
For the particular data used for this research question it would be best to refresh the add-on file on a yearly basis to keep a well updated query.

**D1: Refresh Period Explanation**  
My reasoning for choosing a yearly refresh period for the add-on file is because the only data I ultimately use in my query from the ‘survey\_responses’ table is the ‘timely\_responses’ column. While I do use the weekly outage data from the original customer table, it is unlikely for a customer to want to change their devices more than a few times a year. So, weekly/monthly refreshes are too frequent, and quarterly updates likely won’t paint as clear of a picture of the query results as a yearly refresh would since the equipment failure of customers is only taken into account on a yearly basis.

\--Clear and Restore Add-On Table Data  
DROP TABLE IF EXISTS Survey\_Responses  
CASCADE;

Copy Survey\_Responses  
FROM 'C:\\LabFiles\\Survey\_Responses.csv'  
Delimiter ','  
CSV HEADER;

**F: Data Sources**

*PostgreSQL Tutorial. (2024, January 22). PostgreSQL UPDATE. [https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-update/](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-update/)*

W3Schools. (n.d.). SQL CASE Expression. [https://www.w3schools.com/sql/sql\_case.asp](https://www.w3schools.com/sql/sql_case.asp)

[image1]: <data:image/png;base64,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>