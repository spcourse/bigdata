# Climate debate

![](../../assets/KaartNederlandKlein.png){:.inline}

Let's do our part for the climate discussion and analyze the data provided by the ECA (European Climate Assessment) [available](https://www.ecad.eu/) in big data files. We'll limit ourselves to the data pertaining to the maximum and minimum temperatures for each day measured in De Bilt since 1901.

> **Making the problem smaller:** One of the key skills to practice in this assignment will be reducing a problem to something simpler, where you can easily print all the steps (without becoming impossible to keep track off) and then actually still verify the solution is correct. Having a data set that is too large too print and verify is a very common problem in data processing, and so we'll explicitly practice with this during this assignment.

Files:

- [DeBiltTempMaxOLD.txt](../../data/en/DeBiltTempMaxOLD.txt)
- [DeBiltTempMinOLD.txt](../../data/en/DeBiltTempMinOLD.txt)

Download the files, open them and read the headers (at the top of the file) on how the data has been formatted. In the files we can see the maximum and minimum temperature on January 1st 1901 were -3.1 and -6.8 degrees Celsius, respectively.

*Note that the temperature in the files is given in 10th of degrees, so 18.5 degrees Celsius would be `185`, as also described in the header. Make sure you understand the structure of these files before moving on to the next step.*

Create a program named **weather1.py**. It should read the datafiles.

## Constraints

Throughout the following assignment:

* You are allowed to import the `matplotlib` and `math` libraries.

* You are **not allowed to import** any other python libraries, especially not the `csv` library. You're supposed to read the file using basic python operations such as `open()`, `close()`, `split()`, and [`strip()`](/python/en/strings#string-methods).

* You cannot use the functions `min()`, `max()`, and `.index()`

### Assignment

The first lines in the datafile contain all sorts of clarification and extra information. It is important to keep this information in the file, to make sure that anyone who reads the file can understand its contents. However, our _program_ doesn't need them, so we should implement it in such a way that it _skips_ these lines when it processes the file.

Write a function named `read_data()` that accepts a `filename` and returns two lists: one with all dates, and one with all temperatures. The function should skip all lines containing information about the dataset, and only load the dates and temperatures of the measurements into lists. Look for a distinguishing feature or marker in the lines of data or in the lines preceding the data. Only begin storing the data into the list of dates and temperatures when this condition is satisfied!

> **Making the problem smaller:** In order to filter out the lines with extra information, you will need to find some condition that can distinguish the relevant lines. To test your condition, it would be useful to print each of the lines *and add an extra print when your condition is met*. However, this would result in way too many prints for these large data files. Instead, you can make the problem smaller by only copying a few of the lines to a new file and using this file to test your solution first.

You should be able to load all data through:


    max_dates, max_temps = read_data('DeBiltTempMaxOLD.txt')
    min_dates, min_temps = read_data('DeBiltTempMinOLD.txt')


Where `max_dates` and `min_dates` are both lists of dates (like `'19670513'`), and `max_temps` and `min_temps` are lists of temperatures in degrees C with at most one decimal (like `24.5`).

***Tip:*** for the temperatures you will have to do some basic conversions.

## Testing

    checkpy weather1