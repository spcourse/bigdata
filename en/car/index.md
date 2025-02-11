# Assignment: Sensor data

A mobile phone contains many delicate sensors that collect information about the position, speed and acceleration of the device. We have collected these inputs during a car ride and stored the data in a file with a frequency of 1[Hz]. We started collecting the data when the car was located on the A4 highway where it joins the A10 highway. We stopped collecting data when the car arrived at the Nikhef.

![Map of the route](../../assets/KaartAmsterdamKlein.png)

The sensor data is available in the file `CarRideData.csv` and can be downloaded via the following link:

[CarRideData.csv](../../data/en/CarRideData.csv)

At the top of the file is a short short description about the information contained in each field. This is typically how a data file is formatted: easy to read automatically, but sometimes it lacks clear descriptions of what each field precisely is. It should still be manageable to deduct how to use each field. So first try to figure out which data is contained in what field and how each part of it is represented, before discussing with your fellow students about the data file. It's (a) good practice!

> Note that the speeds in the data are given in meters per second ($$m/s$$), not kilometers an hour. So you might have to convert the speeds in some places.

Write a program **car_ride.py** that traverses the data file, processes said data and answers the following questions.

## Specifications

* Create a graph of the speed of the car (km/h) as a function of the time and use the data to estimate the traveled distance in total.

* Create a graph of the position of the car by making a plot of the latitude and longitude. Color the route green where the speed of the car was more than 50 km/hour. Color the route red where the speed of the car was less than 50 km/hour.

* Also make sure your program prints the total travelled distance (in meters).

## Constraints

* You are allowed to import the `matplotlib` and `math` libraries.

* You are **not allowed to import** any other python libraries, especially not the `csv` library. You're supposed to read the file using basic python operations such as `open()`, `close()`, `split()`, and [`strip()`](/python/en/strings#string-methods).

## Testing

Now you're ready to test with checkpy:

    checkpy car_ride
