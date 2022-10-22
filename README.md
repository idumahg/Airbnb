# What does the data say about AirBnB in Austin.
_________________________________________________
In this project, I used the CRISP-DM Process to analyse Austin Airbnb data from September 18, 2019 to October 8, 2020. 
The data is sources from the following website `https://www.kaggle.com/datasets/clnguyen/austinairbnbs20191112` 
The questions I want to explore using this dataset are the following:

1. Is there any seasonal variability in prices and room availability?
2. What are the busiest time of the year to visit Austin?
3. Are there properties of the listing associated with high price?
4. Can we predict accommodation price using listing features.

I answer these questions, by understanding and preparing the data, model the data, and deploy the result to Medium.

# Data Description
The data I used for my analysis are described briefly below:
- `listings_full.csv`: This contains information about all the Airbnb property listed in Austin within the time period. 
There are $11,339$ unique listings and $106$ features. The features contains different information about each unique 
listing including a column that specifies the price of each listing.
- `calendar.csv`: has information about the daily property listings in Austin. It has $4,138,735$ calendar listings 
and $7$ columns that include columns such as *listing_id, date, available, price, adjusted_price, minimum_nights, maximum_nights*.
- `data_dictionary.csv`: This contains description of the columns in the listings.csv and calendar.csv.

# Regression Model
After cleaning the data, and doing the necessary pre-processing, we have $11339$ rows, and $41$ columns in our `listings.csv`. Of these $41$ 
columns, $12$ are categorical variables which are One-Hot-Encoded, and $29$ are continuous variables. 

Using Linear regression gave very poor result. The r2-score for training data was $0.50$ while for testing, it was $0.40$. 
Therefore, I had to use Random Forest Regressor. With Random forest, we had a r2-score of $0.98$ with train data, and $0.78$ with test data.

# Summary of result
- It is busiest to go to Austin in September as we have fewer listings available in that month. In addition, you have fewer rooms available between the months of April — September.
- There is a greater percentage of Entire homes/apartment room type listed in Austin (about 70% of the listings). While there are fewer Hotel room types.
- There is more variation in the price for Entire home listings. You have higher average prices (in the range of $460) in the months of April — August, and cheaper average prices (less than $340) in the months of January, February, November and December.
- The features that are of more importance in predicting the price of a listing are: `calculated_host_listings_count`, `host_total_listings_count`, 
`calculated_host_listings_count_entire_homes` and `host_listings_count`.
