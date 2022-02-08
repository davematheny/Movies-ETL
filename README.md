# Movies-ETL By David Matheny on 02/26/2022

# Notes:  
Since I couldnt install Postgres locally I had to use an Azure instance.  This caused issues with the to_sql from the library from sqlalchemy import create_engine.  The create_engine only works with a local instance of Postges, so instead I had to insert the data into the database with psycopg2, which was much more challenging. Hardest part was finding the right batchsize for ratings. 
https://docs.microsoft.com/en-us/azure/postgresql/connect-python
https://www.geeksforgeeks.org/how-to-insert-a-pandas-dataframe-to-an-existing-postgresql-table/



# Deliverable 1 Requirements
You will earn a perfect score for Deliverable 1 by completing all requirements below:

An ETL function is written to read in the three data files. (10 pt)
The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
​The function converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
​The function converts the MovieLens ratings data file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)

# Deliverable 2 Requirements
You will earn a perfect score for Deliverable 2 by completing all requirements below:

The TV shows are filtered out, and the wiki_movies_df DataFrame is created. (3 pt)
A try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs. (5 pt)
The extraction and transformation of the Wikipedia data in the ETL function does the following:
A list comprehension is used to keep columns with non-null values. (3 pt)
The non-null box office data is converted to string values using the lambda and join functions. (3 pt)
A regular expression is used to match the six elements of "form_one" of the box office data. (2 pt)
A regular expression is used to match the three elements of "form_two" of the box office data. (2 pt)
The following columns are cleaned in the Wikipedia DataFrame: (8 pt)
The box office column
The budget column
The release date column
The running time column
​The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file. (4 pt)

# Deliverable 3 Requirements
You will earn a perfect score for Deliverable 3 by completing all requirements below:

The extraction and transformation of the Kaggle metadata using the ETL function does the following:
The Kaggle metadata is cleaned. (4 pt)
The Wikipedia and Kaggle DataFrames are merged. (3 pt)
The following is performed on the merged Wikipedia and Kaggle DataFrames to create the movies_df: (8 pt)
Unnecessary columns are dropped.
A function is used to fill in the missing Kaggle data.
The movies_df DataFrame is filtered to keep specific columns.
The movies_df DataFrame columns are renamed.
The extraction and transformation of the MovieLens ratings data using the ETL function does the following:
The ratings counts are cleaned. (3 pt)
The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame. (4 pt)
The empty values in the movies_with_ratings_df DataFrame are filled with “0”. (3 pt)
The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file. (5 pt)

# Deliverable 4 Requirements
You will earn a perfect score for Deliverable 4 by completing all requirements below:

The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png. (5 pt)
The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png. (5 pt)
The elapsed time to add the data to the database is displayed in the ETL_create_database.ipynb file. (5 pt)

## Results
### movies 6,052
![Results1](resources/movies_query.png)
### ratings 26,024,289
![Results2](resources/ratings_query.png)
