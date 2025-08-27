# Summer days and tropical days

Create a file called `weather4.py` and answer the question below.

### Assignment

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
plt.savefig("demo.png")
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
plt.savefig("demo.png")
~~~
</details>


## Testing

    checkpy weather4