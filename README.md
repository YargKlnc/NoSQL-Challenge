# NoSQL-Challenge
# UofT Data Analytics by YK

![image](https://github.com/YargKlnc/NoSQL-Challenge/assets/142269763/1a2afaab-d943-4cec-a210-f426e6c40b0d)

### Instructions
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. This work has been completed for the editors of a food magazine; 'Eat Safe, Love', to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.



Part 1: Database and Jupyter Notebook Set Up

    1.The data provided in the establishments.json file imported from Terminal. The database uk_food and the collection establishments were named. The text used to import the data was copied from Terminal

    
    2.PyMongo and Pretty Print (pprint) libraries were imported

    
    3.An instance of the Mongo Client was created

    
    4.Created database and properly loaded data were confirmed:
        
        o	The databases in MongoDB were listed. Confirmed that uk_food was listed
        
        o	Collection(s) in the database were listed to ensure that establishments were there
        
        o	One document was found and displayed in the establishments collection using find_one and displayed with pprint


    5.Assign the establishments collection to a variable to prepare the collection for use.



Part 2: Updating the Database

The magazine editors have some requested modifications for the database:


    1.An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked to include in the analysis


    2.BusinessTypeID for "Restaurant/Cafe/Canteen" was founded and returned only the BusinessTypeID and BusinessType fields


    3.The new restaurant was updated with the BusinessTypeID 


    4.The magazine is not interested in any establishments in Dover, so how many documents contain the Dover Local Authority was checked. Any establishments were removed within the Dover Local Authority from the database, and the number of documents were checked to         ensure they were deleted


    5.Some of the number values are stored as strings, when they should be stored as numbers.
        
        1.	Update_many was used to convert latitude and longitude to decimal numbers
        
        2.	Update_many was used to convert RatingValue to integer numbers



Part 3: Exploratory Analysis

'Eat Safe, Love' magazine had specific questions they need to get answered, which will help them find the locations they wish to visit and avoid.

    Below were taken into consideration while exploring the dataset:
    
•	RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
o	Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.
•	The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.
Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.
Unless otherwise stated, for each question:
•	Use count_documents to display the number of documents contained in the result.
•	Display the first document in the results using pprint.
•	Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.

1.	Which establishments have a hygiene score equal to 20?

2.	Which establishments in London have a RatingValue greater than or equal to 4?
    Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.

3.	What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
Hint: You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.

4.	How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
Hint: You will need to use the aggregation method to answer this.
