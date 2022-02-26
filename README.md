# Surfs Up

## Project Overview
The purpose of this project was to utilize SQLAlchemy queries to filter weather information in order to compare temperature statistics in June and in December. This information will be used primarily to determine the viability of surf shops being open year round. 

## Results

### June

Utilizing the following query we were able to retrieve the temperature data for the month of June.

<img width="412" alt="image" src="https://user-images.githubusercontent.com/94754972/155861674-1acd8891-99f7-4a55-8462-2f8482c7ce35.png">

The results of this query were translated into a DataFrame from which we were able to calculate the summary statistics needed. 

<img width="58" alt="image" src="https://user-images.githubusercontent.com/94754972/155861630-c4272b8b-d99e-4f1b-8fa5-502a6d3b3574.png">

### December

Utilizing the following query we were able to retrieve the temperature data for the month of December.

<img width="418" alt="image" src="https://user-images.githubusercontent.com/94754972/155861699-09a77e73-543d-4de8-a62a-f8b8f6cbd412.png">

The results of this query were translated into a DataFrame from which we were able to calculate the summary statistics needed. 

<img width="64" alt="image" src="https://user-images.githubusercontent.com/94754972/155861712-19cca157-1c0b-4ea8-b522-6a6dee4cf338.png">


### Comparison

- The mean temperatures in June and December are less than 4 degrees apart, indicating there is not a drastic change.

- While the means are close between the two months, the minimum temp in December was 8 degrees lower. So while the averages are not too different, there will be days in December that are notably colder than the mean.

- The maximum temperatures were also close with June only being 2 degrees higher than December.



## Summary

When comparing the summary statistics between the two months we can see that on average the temperatures are quite similar which is promising from the standpoint of viability of business year round. The biggest difference is that while the averages are close, the range of temperatures in December is greater so there is a possibility that some days throughout the month would be expected to generate less business. 

### Additional Weather Statistics

Using additional queries with the same database available statistics for precipitation in June vs December.

june_precipitation = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()

dec_precipitation = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
