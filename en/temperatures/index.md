# Climate debate

![](../../assets/KaartNederlandKlein.png){:.inline}

Let's do our part for the climate discussion and analyze the data provided by the ECA (European Climate Assessment) [available](http://eca.knmi.nl/dailydata/predefinedseries.php) in big data files. We'll limit ourselves to the data pertaining to the maximum and minimum temperatures for each day measured in De Bilt since 1901.

> **Making the problem smaller:** One of the key skills to practice in this assignment will be reducing a problem to something simpler, where you can easily print all the steps (without becoming impossible to keep track off) and then actually still verify the solution is correct. Having a data set that is too large too print and verify is a very common problem in data processing, and so we'll explicitly practice with this during this assignment.

Files:

- [DeBiltTempMaxOLD.txt](../../data/en/DeBiltTempMaxOLD.txt)
- [DeBiltTempMinOLD.txt](../../data/en/DeBiltTempMinOLD.txt)

Download the files, open them and read the headers (at the top of the file) on how the data has been formatted. In the files we can see the maximum and minimum temperature on January 1st 1901 were -3.1 and -6.8 degrees Celsius, respectively.

*Note that the temperature in the files is given in 10th of degrees, so 18.5 degrees Celsius would be `185`, as also described in the header. Make sure you understand the structure of these files before moving on to the next step.*

Create a program named **temperature.py**. Eventually, it should read the datafiles and answer the questions below.

### Assignment 0: reading the data

The first lines in the datafile contain all sorts of clarification and extra information. It is important to keep this information in the file, to make sure that anyone who reads the file can understand its contents. However, our program should be implemented in such a way that it skips these lines when it processes the file.

Write a function named `read_data()` that accepts a `filename` and returns two lists: one with all dates, and one with all temperatures. The function should loop over the data until it passes all lines containing extra information. Try to find something that is indicative of the lines containing data (or some marker in the lines just before it), and only start saving the data to your list of dates and temperatures when this condition is met.

> **Making the problem smaller:** In order to filter out the lines with extra information, you'll need to find some condition that can distinguish the relevant lines. To actually test this, it would be very useful to print each of the lines *and if your condition is met*, but this would result in way too many prints for these large data files. Instead, you can make the problem smaller by only copying a few of the lines to a separate new file and using this file to test your solution first.

You should be able to load all data through:


    max_dates, max_temps = read_data('DeBiltTempMaxOLD.txt')
    min_dates, min_temps = read_data('DeBiltTempMinOLD.txt')


Where `max_dates` and `min_dates` are both lists of dates like `'19670513'`, and `max_temps` and `min_temps` are lists of temperatures.

> **Tip:** What datatype should your temperatures be? Is there anything we need to do to the temperatures to make it more readable or easier to work with in the rest of our program? Check the information in the header (the first part) of the `.txt` files.

### Assignment 1: extreme temperatures

What were the highest and lowest temperatures that were measured in De Bilt since the start of the 20th century? What days were they measured?

Write two functions named `get_highest_temp()` and `get_lowest_temp()` that return the highest and the lowest temperatures and their respective dates. Each function should accept two arguments: a list of dates and a list of temperatures". Calling the functions and getting their results should look as follows:

    highest_temp_date, highest_temp = get_highest_temp(max_dates, max_temps)
    lowest_temp_date, lowest_temp = get_lowest_temp(min_dates, min_temps)

*You are supposed to write a loop that finds the minimum and maximum yourself. So, you're not allowed to use built-in functions like `min()`, `max()`, `.sort()`, or `sorted()` for this exercise. There should be no `print` statements within your `get_highest_temp()` and `get_lowest_temp()` functions.*

> **Making the problem smaller:** Verifying your code is finding the correct minimum and maximum can also be difficult working when with these large temperature and date lists. One possible solution is to make some simple test lists with a few elements and try those first. Also try to experiment with some different *edge* cases your code might encounter, like when the maximum is actually the first or the last element in the list. This serves to try and ensure your code works in all cases, and not just the one small test you wrote first.

Make sure your program calls the functions as above, and then *afterwards* `print`s the dates properly to the screen. For this you should **not** print:

     Max 34.5 at 19670513

but instead write out the entire month, so something like:

     The highest temperature was 34.5 degrees Celsius and was measured on 13 may 1967.

> **Tip:** Make a separate function that takes a number like `19670513` and converts it into a more readable expression like `13 may 1967`. Make use of functions in a logical way! As always, start by making the problem smaller and test your functions with just one simple input first.

<details markdown="1"><summary  markdown="span"> **Extra challenge:** </summary> If you need an extra challenge, find a way to reduce your duplicate code; the code that finds the minimum temperature and its date shouldn't be too different from the code that finds the maximum temperature and its date. Create a third function that can find both the maximum and minimum temperature depending on its inputs; you should only need one extra function argument for this. Call this function in `get_highest_temp()` and `get_lowest_temp()`. _This extra challenge is not a required part of the exercise._
</details>

### Assignment 2: cold colder coldest

What is the longest period of uninterrupted days that had no temperatures above or equal to 0◦C (i.e. **maximum** temperature below 0◦C)? What was the date of the last day of this period of time?

Write a function named `get_longest_freezing()` that returns both the longest number of days with uninterrupted freezing temperatures and the date of the last day of this period. The function should accept two arguments: `max_dates` and `max_temps`. Take a good look at the example of the calls to the functions in assignment 1, and think of logical variable names.

> **Making the problem smaller:** For these next few assignments, use the same small test lists from before and print out any intermediate results so you can verify the correctness of your algorithm. Try and consider any edge cases for these problems: Can you think of an example where your code *wouldn't* work? Once you're convinced your code works in all cases, you should of course remove any tests prints from your final function.

Print the answer to both questions in one neatly formatted line, such that `checkpy` understands your output. Remember to reuse any formatting functions you wrote before, and do not put your `print` within the function `get_longest_freezing()`.

### Assignment 3: summer days and tropical days

A day is a summer day when the maximum temperature is 25 degrees Celsius or higher. On a tropical day that maximum temperature would even reach 30 degrees. All tropical days are also summer days. Make a graph where the number of summer days is displayed for each year. Then make another graph that displays the tropical days for each year.

A neat solution to display this data would be to use a barchart. A bar chart can be made by using `plt.bar(x, y)`, where `x` can be either a list of nominal variables (in our case the years) **or** a list of coordinates on which to center the bars, and where `y` is the height of the bars (summer or tropical days). An example using nominal values:

~~~
import matplotlib.pyplot as plt

animals = ['Ox', 'Hippopotamus', 'Elephant', 'Kangaroo']
weights = [1100, 1400, 3000, 50]

plt.title('Animal weight')
plt.xlabel('Animal')
plt.ylabel('Weight (kg)')
plt.bar(animals, weights)

plt.show()
~~~

Write a helper function that creates and plots a barchart and name it appropriately. The function should get a list of years, and a list containing a number for each year. Call the function two times, once with the data for summer days, and once with tropical days.

<details markdown="1"><summary  markdown="span"> **Extra challenge:** </summary> If you are up for a challenge, you can also use coordinates and create a barchart that has both summer and tropical days in it! Have a look at and then run the example below:

~~~
import matplotlib.pyplot as plt

schools = ['Preschool', 'Primary', 'Secondary']
blue = [12, 8, 19]
green = [9, 13, 2]

# This is horrible design, can you improve it?
x_ticks = [1, 2, 3]
x_blue = [0.8, 1.8, 2.8]
x_green = [1.2, 2.2, 3.2]

bar_width = 0.4
plt.bar(x_blue, blue, bar_width, color='blue', label='blue')
plt.bar(x_green, green, bar_width, color='green', label='green')

plt.title('Color Preferences')
plt.xticks(x_ticks, schools)
plt.legend()
plt.show()
~~~
</details>

### Assignment 4: first heat wave

In the Netherlands we speak of a heat wave when the maximum temperature has been 25◦C or higher (summer days) for at least five uninterrupted days of which at least three days had maximum temperatures of at least 30◦C (tropical days).

Write a function named `get_first_heat_wave()` that returns the *first* year that a heatwave was found within the dataset following this definition. The function should accept two arguments: `max_dates` and `max_temps`.

> **Making the problem smaller:** This problem is a little trickier then it might look at first glance. If you're code is not giving the correct output right away, remember to try to create some smaller lists and test with those first.

Print the result of the function in a neatly formatted line.

### Design: clean code and clean output

Make sure the code of all your assignments is written in multiple functions. Break up functions where needed. Do not use global variables from within functions; make sure that required variables are always passed as parameters to the function (ask an assistant if this is not clear)!

There are a couple of statements that need to be `print`ed and one graph has to be created. Make sure the requested information is `print`ed on separate lines, in the correct order, and that all `prints` are outside the requested functions.

Try to collect all executing statements in one place; make sure you first define all functions, and then call each of them.

## Testing

Now you're ready to test with checkpy:

    checkpy temperature
