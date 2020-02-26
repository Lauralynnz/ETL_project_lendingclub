# ETL_project_lendingclub
Extract, Transform, and Load loan data from a bank

I’m fascinated by consumer personal finance data. So for this assignment, I went on the hunt for a database with banking and/or loan information. Turns out a couple of banks do share this info:
	Lending Club offers csv downloads of quarterly loan data if you sign up for their service
	Prospect Bank has an API you can access if you apply for permission
Both banks offer similar data, but Lending Club has a more robust database that includes co-signer info and more historical info about credit and loan scoring factors. 

Extract:

I downloaded 12 csv files from the Lending Club website to compile 3 years of data.

Here is the following source for my datasets:

https://www.lendingclub.com/statistics/additional-statistics

Transform:

Since the data was in 12 different files, I had to join them all together.
- created a bridge between postgres and my jupiter notebook so I could access my lending_club database in postgres via jupiter notebook
- read the first csv into jupiter notebook to create my first dataframe and see what the data looked like
- created a python loop to run through all the csv files and create one mega file with all the data

Load:

The last step is to load the data into pgAdmin.
- created a postgresSQL table and schema in pgAdmin to hold the data
- mirrored the schema in a dataframe
- loaded the data into the new SQL database

Challenges:

- Finding a usable banking database
- Connecting all the csvs
- Once the csvs were combined, the file was so big it took a long time to run anything.
- Getting the correct variable types for the schema, they weren’t as obvious as what I was looking at in the dataframes


Limitations:

I wanted to pair this data with a geographic dataset from census.gov or data.gov but I couldn’t find what I was looking for. I did pull a pretty robust demographic database from Kaggle. But the Lending Club database includes only state, whereas the Kaggle database is broken down by zip code. I’d have to aggregate the data in the Kaggle database before I can pair it with Lending Club.
