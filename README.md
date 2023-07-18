# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
* Accessing data using APIs

* Cleaning and transforming data using Python

* Loading data into a database using Python

* Performing EDA, including using both statistics and visualizations

* Identifying trends and patterns in data using statistical models

* Interpreting the results of the statistical models

## Process
### Access Data from CityBike API
1. Extract data from CityBike API and add API parameter to Toronto. (Documentation:http://api.citybik.es/v2/)

2. Parse through the Json data and generate datafram cotaining columns city, station name, empty slots, total slots, free bikes, ebikes, latitude, longitude and timestamp.

3. Final datafram has 9 columns and 663 rows of data.

### Access Data from Foursquare API and Yelp API
1. Extract data from Foursquare API with parameter set to Toronto and radius to 1000 m. (Documentation:)

2. Extract data from Yelp API with parameter set to Toronto and radius to 1000 m. (Documentation:)

3. Parse through the Json data of Foursquare and generate datafram cotaining columns id, latitude, longitude and category.

4. Parse through the text data of Yelp API and generate dataframe containing columns id, name, is_closed, latitude, longitude, address, rating and cateogries.

5. Final datafram of Foursquare has 6 columns and 

6. Final datafram of Yelp has 8 columns and 9811 rows.

### Joining Data from Three APIs and Build Database in Sqlite

1. Merged two dataframes in previous step to remove repetitive locations by latitude and longitude.

2. Count the nearby location of each bike station and store the data under column poi_count.

3. Store three dataframes into sqlite database.

4. Identify primary keys of each table.

5. Build relationship between the three tables

### Build Regression Model

1. data preprocessing:
data exploration: the dataset contains 663 entries of rows with 11 variables.
<img width="662" alt="image" src="https://github.com/maybester/Statistical-Modelling-with-Python/assets/73912419/5c8326e1-d0c0-4894-8f44-f5861493411b">

The relationship between poi and free bikes is stronger than other predictors in the graph.

Data cleaning: missing, duplicate, or inconsistent values and remove irrelevant data to ensure the quality of the data.

Data transformation: convert the data into a format suitable for analysis and modelling including data scaling and normalizing.

2. model selection

<img width="759" alt="image" src="https://github.com/maybester/Statistical-Modelling-with-Python/assets/73912419/6e9b0da5-30eb-4d2a-bf9b-b94312e95a8e">


a. the value of R squared is 60% which means the model is capable of explaining 60% of the pattern in the data.

b. total slots of each bike station have positive correlation to the poi numbers of the station, which means if the station neighbour has more poi, the bike station tend to have more slots for bikes. Meanwhile, other variables such as empty_slots, free_bikes have negative correlation to the target poi, which means is the station neighbour has more poi, the station tend to have fewer free bikes and empty slots for more usage of the bike.

c. p-value of the varibles are less than 0.05 which means the coefficient of the variables are statistically significant. the p-value of empty slots and total slots are 0, which means the probability of the relationship between the two variables and the target poi numbers being solely due to natural variation is 0.

4. model evaluation

there are some assumptions of the model are not met thus the results of the model may not generalize vey well.

a. no perfect multicollinearity between predictor variables (vif>10).

b. homoscedascity of residuals is not met since the variance of the residuals are changing.

## Challenges 

the model is not generalizing well due to some assumptions of the linear regression is not met including the multicollinearity between predictor variables and the homoscedascity of residuals. therefore, these factors inceased the noise in data.

<img width="427" alt="image" src="https://github.com/maybester/Statistical-Modelling-with-Python/assets/73912419/0951b73f-c987-4ee8-a51e-4b48d08454b3">


<img width="453" alt="image" src="https://github.com/maybester/Statistical-Modelling-with-Python/assets/73912419/3e83708c-7d8f-464c-af2d-6a40dd585247">


## Future Goals
1. Multi-linear regression conducted to explore correlation between multiple variables besides from poi values such as rating and number of reviews.

2. More categories of poi can be explored in terms of the correlation to free bikes other than just bars and restaurants.
