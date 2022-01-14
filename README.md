# Movies-ETL - Extract, Transform and Load 


## Project Overview

The Amazing Prime, a video streaming company, decided to sponsor a *hackathon*, where participants trying to predict which low budget movies being released will become popular. Participants of a hackathon need a clean data in order to perform analyses for their algorithms. In order to provide organized and clean dataset, this project focuses on *ETL** or **Extract, Transform and Load** process.


## ETL

ETL (Extract, Transform, Load) is an automated process which takes raw data, extracts the information required for analysis, transforms it into a format that can serve business needs, and loads it to a data warehouse. ETL typically summarizes data to reduce its size and improve performance for specific types of analysis.


## Purpose

The purpose of this project is to gather movie data from both wikipedia and kaggle to create a database and preform analysis. For this process we extracted the neccessary data from Wikipedia and Kaggle using python's pandas library and transform the data into a working dataframe, then loaded it to PostgreSQL.


## Resources

  - Data Sources: 

    -	Wikipedia web scrape [JSON file](Data/wikipedia-movies.json)
    -	Kaggle data from [Kaggle.com](https://www.kaggle.com/rounakbanik/the-movies-dataset) -two files: movies_metadata.csv and ratings.csv

  - Jupyter Notebook
  - Python 3.7.6
      - Dependencies
      - Python Pandas library
      - Python Numpy library
      - Python MatPlotLib library
      - Python json library
    -	Pytho re library
    -	sqlalchemy library , create_engine
    -	psycopg2 library

  - PostgreSQL and PgAdmin


## Overview of the code

The goal of this analysis is to create automated pipeline that extracts, transform and loads data. This analysis consists of four parts, where each step is building up from beginning of extracting data and function testing, through transformation and cleaning process to its final step connect and load to the database. The entire process of ETL can be executed with a single call of the function.

1.	**ETL Function to Read Three Data Files [ETL_function_test.ipynb](ETL_function_test.ipynb)**
    - Data is extracted from the website in JSON and CSV formats.
    - Data is transformed into Pandas data frames.
    - JSON file requires extra step – loading file first and then transforming into data frame.

2.	**Extract and Transform the Wikipedia Data [ETL_clean_wiki_movies.ipynb](ETL_clean_wiki_movies.ipynb)**
    - Function *clean_movie* combines scattered data of alternative languages into one column *alt_titles*. 
    - Its subfunction *change_column_name* organizes column names into consistent pattern.
    - In the function *extract_transform_load* the transformation process of wiki movies data begins and includes:
 
         - Python **list comprehensions**.
         - apply() and map() methods in combination with **lambda functions**.    
         - regular expressions or **RegEx**.
        
3.	**Extract and Transform the Kaggle data [ETL_clean_kaggle_data.ipynb](ETL_clean_kaggle_data.ipynb)**
    - Function *extract_transform_load* gets new tasks for cleaning Kaggle data and includes:
    
        - Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
        - Filling missing values and filtering unwanted columns.
        - Merging data frames using *pd_merge* method.
        
4.	**Create the Movie Database [ETL_create_database.ipynb](ETL_create_database.ipynb)**
    - Finally, the function in its final step connects to the database by **sqlalchemy** library and **to_sql** method. 
    - Complete ETL process can be executed with a single function *extract_transform_load* call.


