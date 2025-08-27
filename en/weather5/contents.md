# First heat wave

Create a file called `weather5.py` and answer the question below.

### Assignment

In the Netherlands, a heat wave is a period of at least five summers days (maximum temperature of at least 25◦C). The period should also contain at least three tropical days (maximum temperature of at least 30◦C). For example the series of these maximum temperatures would constitute a heat wave: 30, 25, 26, 25, 31, 33.

Write a function named `get_first_heat_wave()` that returns the *first* year that a heatwave was found within the dataset following this definition. The function should accept two arguments: `max_dates` and `max_temps`.

Print the result of the function in a neatly formatted line.

> **Making the problem smaller:** This problem can be a little trickier than it might look at first glance. If your code is not giving the correct output right away, remember to go back to some smaller test lists and debug with those first.

### Design: clean code and clean output

Make sure the code of all your assignments is written in multiple functions. Break up functions where needed. Do not use global variables from within functions; make sure that required variables are always passed as parameters to the function (ask an assistant if this is not clear)!

There are a couple of statements that need to be `print`ed and one graph has to be created. Make sure the requested information is `print`ed on separate lines, in the correct order, and that all `prints` are outside the requested functions.

Try to collect all executing statements in one place; make sure you first define all functions, and then call each of them.

## Testing

    checkpy weather5
