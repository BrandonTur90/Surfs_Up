# Surfs_Up

## Overview
The purpose of this project was to run an analysis on weather data stored in a SQLlite database
to determine the viability of a surf and ice cream shop in Oahu, Hawaii. To do this it was necessary
to extract data from the SQLite database using SQLAlchemy, put it into dataframes using Pandas, and 
then create a statistical analysis of the dataframes. In addition a Flask App was created using the 
SQLite database to interact with the data directly. The last task was to focus on the temperature
of the months of June and December to further determine year-round sustainability.


## Results

![June](/Resources/June_Temps.PNG)

![December](/Resources/December_Temps.PNG)

From the statistics above we can surmise:

* December's min temperature is 8 degrees (56F) colder than June's (64F)
* June's max temperature (85F) is not much hotter than December's (83F)
* The median temperature between both months is within the 70s, with June's being 75F, and December 
  being 71F.


## Summary
After running all the data it would seem that a surf and ice cream shop could be sustainable 
all year round. Although temperatures in December can dip a little, normally it's above 
70F degrees. Although the temperature might not be too different in both months, it might be
worth examining how different the precipitation is between June and December. You could run the
following two queries, along to find out.

```
june_precip = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
```

```
dec_precip = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
```

