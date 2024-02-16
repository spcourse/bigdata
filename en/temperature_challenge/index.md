## Temperature challenges

These assignments are not required, but enable you to practice some more of the concepts of this module.

### Challenge 1:

If you are up for a challenge, you can also use coordinates and create a barchart that has both summer and tropical days in it!

Have a look at and then run the example below:

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

### Challenge 2: first heat wave

In the Netherlands we speak of a heat wave when the maximum temperature has been 25◦C or higher (summer days) for at least five uninterrupted days of which at least three days had maximum temperatures of at least 30◦C (tropical days).

Write a function named `get_first_heat_wave()` that returns the *first* year that a heatwave was found within the dataset following this definition. The function should accept two arguments: `max_dates` and `max_temps`.

Print the result of the function in a neatly formatted line.

> **Making the problem smaller:** This problem can be a little trickier then it might look at first glance. If your code is not giving the correct output right away, remember to go back to some smaller test lists and debug with those first.

**This challenge can be tested by checkpy!** You can just use the original test for this:

    checkpy temperature
