# Movies-ETL


## Purpose

Amazing Prime Video, a movie platform has decided to conduct a hackathon to connect with the local coding community. Inorder to carry on the hackathon the students need to extract movie data from Wikipedia , Kaggle and MovieLens ratings and determine the popular movies. We have followed the following process :
1. We have created an **ETL**(Extract, Transform and Load) pipeline from raw data to a SQL database. 
2. Extract data from different sources using Python.
3. Clean and transform data using Pandas.
4. Use regular expressions (Regex) to parse the data.
5. Load data with PostgreSQL and verify it in PgAdmin.

## Results 

## Extract :

For carrying out our analysis the fisrt step will be extracting the data. Using Pandas we created a function to extract Wikipedia, Kaggle and Ratings data from the JSON and CSV files.

<img width="918" alt="extract" src="https://user-images.githubusercontent.com/88418201/137409164-bb172e91-1f84-49a1-875c-9ac6d9917062.png">

1. ### Wikipedia movies data extracted from JSON file (193 columns extracted) :

<img width="1363" alt="wiki" src="https://user-images.githubusercontent.com/88418201/137409330-fdaa25f0-f10b-4ed8-a8d7-7f17d83af5fd.png">

2. ### Kaggle movies data extracted from CSV file (24 columns extracted) :

<img width="1336" alt="kaggle" src="https://user-images.githubusercontent.com/88418201/137409406-4dab2531-4219-4fd3-97e8-46a4d7c2b414.png">

3. ### Ratings of movies extracted from CSV file :

<img width="384" alt="ratings" src="https://user-images.githubusercontent.com/88418201/137409553-e75ba71c-8ce5-4579-926f-a6720496ec88.png">


## Transform :

After extracting the Wikipedia, Kaggle and Ratings data we need to transform this data by doing some cleaning. We need to change the datatypes of some of the columns inorder to load the correct format of the data. 
In the Wikipedia movies dataframe and Kaggle movies dataframe we transformed the Box office column by using the Regex function to fetch all the possible clean Box office data. Similarly we also cleaned the Budget, Release Date and Running time columns using Regex.

Below is the cleaned and transformed Wikipedia movies dataframe (23 columns extracted) :

<img width="1337" alt="wiki_clean" src="https://user-images.githubusercontent.com/88418201/137411507-5b9558cf-d660-4ce5-ab4d-bdd9d13c9573.png">

Below is the merged Wikipedia and Kaggle Movies dataframe into a new Movies dataframe :

<img width="1320" alt="Movies_df(merge)" src="https://user-images.githubusercontent.com/88418201/137411903-296bef20-6b11-4e36-ac74-63661c03fc2f.png">

Below is the merged Movies and Ratings dataframe :

<img width="1319" alt="movies_ratings" src="https://user-images.githubusercontent.com/88418201/137412110-e13ddfd6-4aff-4990-a698-9467fc573869.png">

## Load :

Using PostgreSQL we will be loading our transformed data into the Movies database :

<img width="755" alt="DB" src="https://user-images.githubusercontent.com/88418201/137412354-dcec97c1-8201-4a8a-bfda-979731cf8376.png">

<img width="751" alt="load" src="https://user-images.githubusercontent.com/88418201/137412357-d424e615-617a-4e5d-8c0b-f1ad9a0ce1a4.png">

Using PgAdmin we will be then verifying the loaded tables into the database :

<img width="448" alt="movies_query" src="https://user-images.githubusercontent.com/88418201/137557285-2796808e-220d-4ed3-9870-4926d5b1889a.png">

<img width="365" alt="ratings_query" src="https://user-images.githubusercontent.com/88418201/137557290-afde9ae6-292d-40ba-9927-fec48d190a16.png">


## Summary

Inorder to carry a hackathon, a Wikipedia JSON file , Kaggle and Ratings CSV files were extracted and then transformed into a readable format using Pandas, Regex functions and then the Movies and Ratings table were loaded into the database.
