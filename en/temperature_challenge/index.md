## Temperature challenges

If you do not have time for these challenges, or do not know how to approach it, **you are allowed to skip it**. However, this is also a great opportunity to show your understanding of the design concepts of this week!


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

### Challenge 3:

On the "Learn to analyse and process a dataset" practice-page you have copied and pasted a program that can calculate the total number of goals van Basten has made for his club and find in which seasons van Basten scored more than 20 goals. The program does everything in a single loop, which leads to minimal code, but makes it more difficult to reuse parts for different but similar data analysis that we could want to do with the data. In `temperature.py` you have done a similar set of tasks, but separated the different "phases" of the program into functions.

As an exercise in design, try to think of ways to improve this program, but not change its functionality. Code design is very difficult to learn, and requires thinking and rewriting code, so try to find another student to discuss with!
