# About
An analysis of the effect that a house's proximity to other locations of interest (parks, schools, etc.) has on its price. <br>
The goal is to determine whether or not the addage "location, location, location" holds true consistently across different cities and regions. 

The target variable is the price per square foot of a given house. The features are the house's distances to a variety of locations of interest (park, school, restaurant, hospital, etc). 

Data is collected for four metro areas: Los Angeles, Dallas, Chicago, and Washington DC. <br>
These metros were selected as they are all very large and populous, yet represent different regions of the US. NYC was not considered as it has a unique urban planning model from the rest of the country. <br>

### Data collection / engineering
A sample of 500 houses was taken from each metro area. Their prices and geo coordinates were provided by Realty Mole Property API. <br><br>
All the locations of interest, their names, and addresses within each metro area were obtained by scraping Yellow Pages and manually filtering out unwanted results (locations misclassified by Yellow Pages). <br><br>
Next, Position Stack API was used to translate the location addresses into geo coordinates. <br><br>
Since GPS coordinates are in an ellipsoidal space, the GeoPy library was used to calculate the distance in miles between each house and every landmark within the same metro area, thereby finding the shortest distance to each landmark type for any given house. This constitutes the final dataset, as the minimum distances are the features to be analyzed. 

# To Do
* For some reason, the distance calculation is returning extremely small numbers.
* The geocoding API still returns sets of duplicate coordinates, even after slowing the request rate at the direction of customer support. As the dataset is quite large, I will try submitting queries in smaller batches. If that doesn't work, then more guidance will be needed.
* I am still in the data generation/processing stage. The actual analysis/modeling still remains. This project is based on a class project wherein the analysis was completed. However, the data had major flaws which render that analysis invalid. 
