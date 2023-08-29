# Crowdfunding_ETL 
# By Dianna Rivera, Patrick Schulze, and Tiffany Conrad
--------------------------------------------------------

# Project Objectives:

•	Extract Data from Excel Files

•	Create the Category and Subcategory DataFrames

•	Create the Campaign DataFrame

•	Create the Contacts DataFrame

•	Create an ERD 

•	Create the Crowdfunding Database


# BreakDown of Tasks: 
--------------------
  •	Create the Category and Subcategory DataFrames - Joint Effort by Dianna, Patrick and Tiffany

  •	Create the Campaign DataFrame - Completed by Dianna

  •	Create the Contacts DataFrame - Completed by Tiffany

  •	Create the Crowdfunding Database - Completed by Patrick


# Repositry Contents: 
--------------------

  •	Resources folder containing the excel data files, all four completed CSV files, and the Database schema

  •	The Jupyter notebook file containing the coding for creating the databases from the excel files

  •	The README file, contain the project overview. 



# Project Objective Overview:  
1.) Extract Data from Excel Files:
-------------------------------
  •	Data was extracted via Pandas from two excel files and imbedded into Pandas DataFrames
  
  •	Each DataFrame was then displayed to confirmed the data was correctly extracted. 
  
  •	This was done to ease later data transformations, data cleaning, as well as DataFrame merges. 

   ![P2 Data extraction](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/d8238a71-9752-439e-9b67-319793def2ca)


2.)	Create the Category and Subcategory DataFrames:
------------------------------------------
  •	Using the list() and .columns functions, the column names are extracted from the first DataFrame, crowdfunding_info_df.
  
  •	These column names are then used to split the “category & subcategory” into two separate columns on the using the str.split function on the  “/”
  
  •	From there, we extracted the unique values within each column, which are further used to determine the number of unique category and subcategory values.

![P2 Numpy Array](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/4218b144-43d1-4212-b0bb-3f17fd35e371)

  
  •	Using numpy arrays and list comprehensions, a list of category ids and subcategory ids are assembled, based on the number of unique values for each respective list. 
  ![P2 category_df](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/1c5972bb-10f5-44da-964b-664e7bb7f059)

  •	These two lists are then combined to create two separate DataFrames, which are then saved to CSV files



3.)	Create the Campaign DataFrame:
----------------------------------
  •	A copy of the original DataFrame is used to create a new data frame with renamed columns.
  
  •	Several of these columns are then converted into float type while others are converted into datetime format. 
  
  •	The date frame is then merged with the Category and Subcategory DataFrames, and the staff_pick, spotlight, category and sub_category columns are then dropped from the merged DataFrame

  •	This DataFrame is then saved to a CSV file


![P2 campaign conversion](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/f037edc1-dcbe-43de-8a0a-3396b39d0c03)
![P2 datetime](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/8bc1f82c-9594-4d73-9fd7-b2e3ae2028f1)



4.)	Create the Contacts DataFrame:
----------------------------------
  •	Data is extracted from the contacts excel file, and transformed into a Pandas DataFrame

  •	Using for loops, the dictionary entries are separated, with the keys becoming the column names, while the values became the column values.

  •	The name column is further split into two columns, for the first and last names respectively. The original name column is dropped.

  •	These columns are then reorganized, the datatype of the DataFrame was checked using the .info() function, and the data was saved to the final CSV file. 


![P2 for loop](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/e1b36b9f-b6a9-4ab5-b51d-e0b5f3d9b50b)
![P2 contacts split](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/5f6715a6-48e2-4ae4-8b79-b9817a591f6a)



5.)	Create an ERD:
----------------------------------
  •	The four CSV files were used to create an ERD in QuickDBD

  •	Each was entered with a full list of their columns and the columns’ data types

  •	 For each database, the primary and foreign keys were notated, alongside any additional constraints

  •	The relationships between each dataset was also depicted, and the information saved to a database schema



6.)	Create the Crowdfunding Database:
----------------------------------
  •	Finally, a new database schema was used to create tables in PgAdmin. 

  •	Each table was created from their respective CSV file, as well as the ERD previously created, with the coordinating column names data types, and keys.

  •	The data from each CSV file was imported into their respective table, then displayed using the SELECT commands. 

  •	This database schema was then saved to a Postgres file in the Resources folder. 



![P2 database schema](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/a9e946fd-3930-4846-95f6-0cfc6b4086c8)
![P2 alteration](https://github.com/TrConrad/Crowdfunding_ETL/assets/133298343/28348883-0b37-447d-99d6-624089b2651d)


# Conclusion: 
-------------

This Project was an exercise in utilizing ETL’s on multiple data sources. We were challenged to extract crowdfunding data from multiple sources, in this case two excel sheets, then transform it into data tables for easier analysis. Once the data was transformed into data tables, it was split into separate columns, several of which were broken down further, such as how the “category & sub-category” column became the “category” and “subcategory” columns. From there, individual columns were converted to different datatypes, while unnecessary columns were removed entirely. Once the data was transformed and cleaned, it was saved to four separate csv files, which were then used to create an Entity Relationship Diagram (ERD), which was created using the QuickDBD website. Once the data types, keys and other constraints were assigned within the ERD, it was saved to a database schema in Postgres file via PgAdmin. A new database schema was then created to create tables, to which the four CSV files we created were then imported. Several Images of the code used within the project have been included within the objectives depicted above. 

