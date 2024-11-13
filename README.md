## Heather Eby and Abigail Husain's Crowdfunding_ETL Project 2

Summary: We transformed data stored in two excel files (crowdfunding.xlsx and contacts.xlsx) in order to create a database with four clean and efficient tables (contacts, category, subcategory, campaign) to make an organized SQL Crowdfunding Database. We split the work into two parts which are described below - Abigail completed Part 1 and Heather completed Part 2.


## Part 1: Created the Category, Subcategory, and Campaign DataFrames
- Data from the crowdfunding.xlsx file was loaded into python using pandas
- Split the category & sub-category column into separate category and subcategory columns in crowdfunding_info_df
- Extracted unique values from category and subcategory columns into categories and subcategories lists
- Counted the number of distinct values in categories and subcategories lists
- Created category_ids and subcategory_ids arrays with values from 1 to 9 and 1 to 24, respectively, using numpy
- Generated lists of strings with prefixes (cat for categories and subcat for subcategories) using list comprehensions
- Constructed a category_df DataFrame with category_id and category columns, and a subcategory_df DataFrame with subcategory_id and subcategory columns, which were then exported as csv files
- Copied the crowdfunding_info_df to create the contacts data frame, renamed columns, and changed data types to the appropriate formats
- Merged in the category and subcategory dataframes to add the category_id and subcategory_id columns
- Dropped unwanted columns and exported the campaign_merged_df data to the campaign.csv file

## Part 2: Created the Contacts DataFrame, PostgresSQL Table Schema, and Loaded Data into Crowdfunding SQL Database
- Data from the contacts.xlsx file was loaded into python using pandas
- Used pandas to create a contact_info_df by iterating through the columns and converting each JSON string to a dictionary, then using the dictionary key values to store the row data in list form
- Manipulated the dataframe to split the name column into first_name, last_name, drop unnecessary columns, and reorder the data
- Exported the contacts_df_clean dataframe into a contacts.csv file
- Inspected all four csv files to establish relationships
- Used QuickDBD to create the table schema and identify the unique values in each table which served as the primary keys, and drew the foreign key relationships between the contact_id, category_id, and subcategory_id fields in their respective tables to the campaign table
- Imported the table schema into PostgresSQL and created the contacts, category, subcategory, and campaign tables
- Loaded the csv files in order of table creation and ran SELECT statements to select all data from each table to verify insertion 
