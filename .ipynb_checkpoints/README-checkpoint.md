# Overview

## Business Objectives

The startup 'Sparkify' has a relational database called sparkifydb to capture its data on songs, artists, users and also records transactions of when a song is played.

Using this data, Sparkify will be able to come up with insights such as:
- Which locations have the highest volume of music usage?
- Which are the most popular artists?
- Are there any seasonal variations? And which are the most common times of day for music usage?

## Schema

The database contains 5 tables:
1. songs
2. artists
3. users
4. time
5. songplays

Each table has a unique ID designed as the primary key. The primary keys of the first 4 tables are referenced as a foreign key in the songplays table. 


## Data Pipeline

The ETL pipeline imports JSON files from the log_data and song_data folders, and inserts relevant rows into their respective tables line by line using for loops. Functions process_song_file and process_log_file are used to do this, with the help of a wrapper function process_data that calls these functions.


## Files/directories in Project

The data folder contains JSON files for song and song play information.

sql_queries.py - SQL queries to drop, create and insert values.
create_tables.py - Creates required tables by importing lists of create and drop queries from sql_queries.py.
etl.py - processes files in data folder and inserts values into tables.

The Jupyter notebooks are for testing and development purpose.


## How to Run this Project

First run the create_tables.py script, and then the etl.py script. The output can be tested using the test.ipynb notebook to run queries.


## References (used the following sources to resolve errors):

- https://stackoverflow.com/questions/9744775/how-to-convert-integer-timestamp-to-python-datetime
- https://webcache.googleusercontent.com/search?q=cache:HXMlTDvtyTUJ:https://stackoverflow.com/questions/695289/cannot-simply-use-postgresql-table-name-relation-does-not-exist+&cd=1&hl=en&ct=clnk&gl=us
- https://www.postgresqltutorial.com/postgresql-char-varchar-text/
- https://github.com/nareshk1290/Udacity-Data-Engineering/tree/master/Data-Modeling