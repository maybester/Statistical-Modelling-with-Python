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

1. Choose number of poi as independant variable and free bikes as dependent variable.

## Results![image](https://github.com/maybester/Statistical-Modelling-with-Python/assets/73912419/adb3cda6-292e-45a2-b65c-853562f02f05)
<img width="794" alt="image" src="https://github.com/maybester/Statistical-Modelling-with-Python/assets/73912419/77b1f474-90b1-4aa4-9845-6eb9e8699f96">

3. results.

![Uploading image.png…]()



## Challenges 
1. Due to the complicated Json data structure, it makes parsing steps not easy.

2. Ambigous documentation in Yelp API caused error in data extracting steps.

## Future Goals
1. Multi-linear regression conducted to explore correlation between multiple variables besides from poi values such as rating and number of reviews.

2. More categories of poi can be explored in terms of the correlation to free bikes other than just bars and restaurants.
