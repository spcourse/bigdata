# Climate debate

![](../../assets/KaartNederlandKlein.png){:.inline}

Let's do our part for the climate discussion and analyze the data provided by the ECA (European Climate Assessment) [available](http://eca.knmi.nl/dailydata/predefinedseries.php) in big data files. We'll limit ourselves to the data pertaining to the maximum and minimum temperatures for each day measured in De Bilt since 1901.

Files:

- [DeBiltTempMaxOLD.txt](../../data/DeBiltTempMaxOLD.txt)
- [DeBiltTempMinOLD.txt](../../data/DeBiltTempMinOLD.txt)

Download the files, open them and read the headers (at the top of the file) on how the data has been formatted. We can see the maximum (minimum) temperature at January 1st 1901 was -3.1 (-6.8) degrees Celsius.

Create a program named **temperature.py**. Eventually, it should read the datafiles and answer the questions below.

### Assignment 0: reading the data

The first lines in the datafile contain all sorts of clarification and extra information. It is important to keep this information in the file, to make sure that anyone who reads the file can understand its contents. However, our program should be implemented in such a way that it skips these lines when it processes the file.

Write a function named `read_data()` that accepts a `filename` and returns two lists: one with all dates, and one with all temperatures. The function should loop over the data untill it passes all lines containing extra information. Try to find something that is indicative of the lines containing data (or some marker in the lines just before it), and only start saving the data to your list of dates and temperatures when this condition is met.

You should then be able to load all data through:


    max_dates, max_temps = read_data('DeBiltTempMaxOLD.txt')
    min_dates, min_temps = read_data('DeBiltTempMinOLD.txt')


Where `max_dates` and `min_dates` are both lists of dates like `'19670513'`, and `max_temps` and `min_dates` are lists of temperatures.

> What datatype should your temperatures be? Is there anything we need to do to the temperatures to make it more readable or easier to work with in the rest of our program? Check the information in the first part of the `.txt` files.

### Assignment 1: extreme temperatures

What were the highest and lowest temperature that were measured in De Bilt since the start of the 20st century? What days were they measured?

Write two functions named `get_highest_temp()` and `get_lowest_temp()` that return the highest and the lowest temperatures and their respective dates. Each function should accept two arguments: a list of dates and a list of temperatures". Calling the functions and getting their results should look as follows:

    highest_temp_date, highest_temp = get_highest_temp(max_dates, max_temps)
    lowest_temp_date, lowest_temp = get_lowest_temp(max_dates, max_temps)

 Make sure your program calls the functions as above, and then `print`s the dates properly to the screen. Don't print:

     Max 34.5 at 19670513

but something like:

     The highest temperature was 34.5 degrees Celsius and was measured at 13 may 1967.

*You are not allowed to use built-in functions like `min()` or `max()` for this exercise. There should be no `print` statements within your `get_highest_temp()` and `get_lowest_temp()` functions.*

**Tip:** make a separate function that takes a number like `19670513` and converts it into a more readable expression like `13 may 1967`. Make use of functions in a logical way!

> If you need an extra challenge, find a way to reduce your duplicate code; the code that finds the minumum temperature and its date shouldn't be too different from the code that finds the maximum temperature and its date. Create a third function that can find both the maximum and minimum temperature depending on its inputs; you should only need one extra function argument for this. Call this function in `get_highest_temp()` and `get_lowest_temp()`. <br><br> _This extra challenge is not a required part of the exercise._

### Assignment 2: cold colder coldest

What is the longest period of uninterrupted days that had no temperatures above 0◦C (i.e. **maximum** temperature below 0◦C)? What was the date of the last day of this period of time?

Write a function named `get_longest_freezing()` that returns both the longest number of days with uninterrupted freezing temperatures and the date of the last day of this period. The function should accept two arguments: `max_dates` and `max_temps`. Take a good look at the example of the calls to the functions in assignment 1, and think of logical variablenames.

Print the answer to both questions in one neatly formatted line, such that `check50` understands your output. Remember to reuse any formatting functions you wrote before, and do not put your `print` within the function `get_longest_freezing()`.

### Assignment 3: summer days and tropical days

A day is a summer day when the maximum temperature is 25 degrees Celsius or higher. On a tropical day that maximum temperature would even reach 30 degrees. All tropical days are also summer days. Make a graph where both the number of summer days and tropical days is displayed for each year. A neat solution would be to use a barchart. Write a function that creates this barchart and name it appropriately.

### Assignment 4: first heat wave

In the Netherlands we speak of a heat wave when the maximum temperature has been higher than 25◦C (summer days) for at least five uninterrupted days of which at least three days had maximum temperatures of at least 30◦C (tropical days).

Write a function named `get_first_heat_wave()` that returns the *first* year that a heatwave was found within the dataset following this definition. The function should accept two arguments: `max_dates` and `max_temps`.

Print the result of the function in a neatly formatted line.

### Clean code and clean output

Make sure the code of all your assignments is written in multiple functions. Break up functions where needed. Do not use global variables from within functions; make sure that required variables are always passed as parameters to the function (ask an assistant if this is not clear)!

You can see above that there are a couple of statements that need to be `print`ed and one graph has to be created. Make sure the requested information is `print`ed on separate lines, in the correct order.

Try to collect all executing statements in one place; make sure you first define all functions, and then call each of them.

## Testing

Now you're ready to test with checkpy:

    checkpy temperature
