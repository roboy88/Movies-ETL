Amazing Prime loves the dataset and wants to keep it updated on a daily basis. Britta needs to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. Create one function that takes in the three files - Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database. The objective is to create a Movie database with ETL data, Wikipedia data, and kaggle data.
Challenge Overview
Prerequisite:

Deliverable 1: Write an ETL Function to Read Three Data Files: Download the ETL_Deliverable1_starter_code.ipynb file and rename it to ETL_function_test.ipynb file.
Deliverable 2: Extract and Transform the Wikipedia Data: Download the ETL_Deliverable2_starter_code.ipynb file and rename it to ETL_clean_wiki_movies.ipynb file.
Deliverable 3: Extract and Transform the Kaggle data: Download the ETL_Deliverable3_starter_code.ipynb file and rename it to ETL_clean_kaggle_data.ipynb file.
Deliverable 4: Create the Movie Database: Make a copy of ETL_clean_kaggle_data.ipynb and rename the file ETL_create_database.ipynb
Deliverable 1: Write an ETL Function to Read Three Data Files
Step 1, create a function to read in the three files and give it a name.

Step 2, read in the Kaggle metadata and MovieLens ratings CSV files as Pandas DataFrames.

Step 3, open the Wikipedia JSON file and use the json.load() function to convert the JSON data to raw data.

Step 4, read in the raw Wikipedia movie data as a Pandas DataFrame.

Step 5, use the code provided to return the three DataFrames.

Step 6, use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.

Step 7, set the three variables in Step 6 equal to the function created in Step 1.

Step 8, set the DataFrames from the return statement equal to the file names in Step 6. In this step, you are reassigning the variables created in Step 6 to the variables in the return statement.

Steps 9-11, check that all three files are converted to a DataFrame.

Steps 12, After you confirm that all three DataFrames are correct, save the ETL_function_test.ipynb file in your Movies-ETL GitHub folder.

Deliverable 2: Extract and Transform the Wikipedia Data
Step 1, add the code from this module for the clean movie function that takes in the argument "movie".

Step 2, add the function you created in Deliverable 1 that reads in the three data files.

Step 3, inside the function you created in Deliverable 1, remove the code that creates the wiki_movies_df DataFrame from the wiki_movies_raw file, then write a list comprehension that filters out TV shows from the wiki_movies_raw file.

Step 4, write a list comprehension to iterate through the cleaned wiki movies list that you created in Step 3.

Step 5, read in the cleaned movies list from Step 4 as a DataFrame.

Step 6, write a try-except block that will catch errors while extracting the IMDb IDs with a regular expression string and dropping any imdb_id duplicates. If there is an error, capture and print the exception.

Step 7, write a list comprehension to keep the columns that have non-null values from the DataFrame created in Step 5, then create a wiki_movies_df DataFrame from the list.

Step 8, create a variable that will hold all the non-null values from the "Box office" column.

Step 9, convert the box office data created in Step 8 to string values using the lambda and join functions.

Step 10, write a regular expression to match the six elements of form_one of the box office data.

Step 11, write a regular expression to match the three elements of form_two of the box office data.

Step 12, add the parse_dollars() function.

Step 13, add the code that cleans the box office column in the wiki_movies_df DataFrame using the form_one and form_two lists created in Steps 10 and 11, respectively.

Step 14, add code that cleans the budget column in the wiki_movies_df DataFrame.

Step 15, add code that cleans the release date column in the wiki_movies_df DataFrame.

Step 16, add code that cleans the running time column in the wiki_movies_df DataFrame.

Step 17, use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.

Step 18, set the three variables in Step 17 equal to the function created in Deliverable 1.

Step 19, set the wiki_movies_df equal to the wiki_file variable.

Step 20, check that your wiki_movies_df DataFrame.

Step 21, add the columns from wiki_movies_df DataFrame to a list.

Deliverable 3: Extract and Transform the Kaggle data
Step 1, add the function you created in Deliverable 1 that reads in the three data files and creates the kaggle_metadata and ratings DataFrames.

Before Step 2, add all the code you wrote for Deliverable 2.

Step 2, below the code that cleans the running time column in the wiki_movies_df DataFrame from Deliverable 2, add the code that cleans the Kaggle metadata.

Step 3, merge the wiki_movies_df DataFrame and the kaggle_metadata DataFrames, then name the new DataFrame, movies_df.

Step 4, drop unnecessary columns from the movies_df DataFrame.

Step 5, add the fill_missing_kaggle_data() function that fills in the missing Kaggle data on the movies_df DataFrame.

Step 6, call the fill_missing_kaggle_data() function with the movies_df DataFrame and the Kaggle and Wikipedia columns to be cleaned as the arguments.

Step 7, filter the movies_df DataFrame to keep the necessary columns.

Step 8, rename the columns in the movies_df DataFrame.

Step 9, transform and merge the ratings DataFrame with the movies_df DataFrame, name the new DataFrame movies_with_ratings_df, then clean the movies_with_ratings_df DataFrame.

Step 10, use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.

Step 11, set the three variables from Step 17 of Deliverable 2 equal to the function created in Deliverable 1.

Step 12, set the DataFrames from the return statement after Step 9 equal to the file names in Step 11.

Step 13, check that your wiki_movies_df DataFrame is the same as in Deliverable 2.

Step 14, check that your movies_with_ratings_df DataFrame.

Step 15, check that your movies_df DataFrame.

After you confirm that all three DataFrames are correct, save the ETL_clean_kaggle_data.ipynb file in your Movies-ETL GitHub folder.

Deliverable 4: Create the Movie Database
Step 1, In the first cell, uncomment the # from config import db_password so this code is working.

Step 2, Remove the return statement, return wiki_movies_df, movies_with_ratings_df, movies_df.

Step 3, After Step 9, Transform and merge the ratings DataFrame, add the code to create the connection to the PostgreSQL database, then add the movies_df DataFrame to a SQL database.

Step 4, Before reading in the MovieLens rating CSV data, drop the ratings table in pgAdmin.

Step 5, Add the code that prints out the elapsed time to import each row.

Step 6, Refactor Step 11 of Deliverable 3 so that you pass in the variables for the files created in Step 10 of Deliverable 3 in the function created in Deliverable 1.

Step 7, Run the program.

Step 8, After the program has finished, run a query on the PostgreSQL database that retreives the number of rows for the movies and ratings tables.

Step 9, After you confirm that the movies table has 6,052 rows and the ratings table has 26,024,289 rows, take a screenshot of each query and the output, then save them as movies_query.png and ratings_query.png, respectively.

Step 10, Save the ETL_create_database.ipynb file in your Movies-ETL GitHub folder.

Step 11, Save the movies_query.png and ratings_query.png files in the Resources folder.

Images of DataFrames and SQL Database Tables
Image of Deliverble 1 wiki_movies_df dataframe image_name

Image of Deliverble 1 kaggle_meta_data dataframe image_name

Image of Deliverble 1 ratings dataframe image_name

Image of Deliverble 2 wiki_movies_df dataframe image_name

Image of Deliverble 2 wiki_movies_df columns list image_name

Image of Deliverble 3 movie_with_ratings_df dataframe image_name

Image of Deliverble 3 movies_df dataframe image_name

Image of Deliverble 4 movies data base count image_name

Image of Deliverble 4 ratings data base count image_name
