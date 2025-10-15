# sql-data-cleaning
Using SQL to clean data
<img width="512" height="338" alt="image" src="https://github.com/user-attachments/assets/47a8a074-b990-405d-8da5-4a65935ce8f1" />
-------------
This is an educational project on data cleaning and preparation using SQL. The original database in CSV format is located in the file club_member_info.csv. Here, we will explore the steps that need to be applied to obtain a cleansed version of the dataset.

## 1. View data
Use query below to view data
````sql
SELECT*from club_member_info cmi 
LIMIT 5;
````
Result:
|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|addie lush|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|      ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|Sydel Sharvell|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|Constantin de la cruz|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|  Gaylor Redhole|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
## 2. Create a cleaned table
create a new table
````sql
CREATE TABLE club_member_info_cleanned (
	full_name VARCHAR(50),
	age INTEGER,
	martial_status VARCHAR(50),
	email VARCHAR(50),
	phone NVARCHAR(50),
	full_address NVARCHAR(50),
	job_title VARCHAR(50),
	membership_date NVARCHAR(50)
````
Result:


## 3. Remove duplicate
````sql
SELECT 
   full_name
   ,age
   ,martial_status
   ,email
   ,phone
   ,full_address
   ,job_title
   ,membership_date 
   ,COUNT(*) as count_duplicate 
 from club_member_info_cleanned cmic 
 group by 
    full_name 
    ,age
    ,martial_status
    ,email
    ,phone
    ,full_address
    ,job_title
    ,membership_date 
  having count(*)>1
````
Result:


