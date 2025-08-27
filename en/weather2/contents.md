# Extreme temperatures

Create a file called `weather2.py` and answer the question below.

***Tip:*** You will need to read the same data again. You can use the `read_data(filename)` function from the previous assignment. But a more elagant solution is to import it from that file. You can do that using the `import` statement:

    # Import the function read_data from `weather.py`. 
    # (This only works when this file and `weather.py` exist in the same folder)
    from weather1 import read_data  
    max_dates, max_temps = read_data('DeBiltTempMaxOLD.txt')
    min_dates, min_temps = read_data('DeBiltTempMinOLD.txt')

### Assignment 

What were the highest and lowest temperatures that were measured in De Bilt since the start of the 20th century? What days were they measured?

Write two functions named `get_highest_temp()` and `get_lowest_temp()` that return the highest and the lowest temperatures and their respective dates. Each function should accept two arguments: a list of dates and a list of temperatures". Calling the functions and getting their results should look as follows:

    highest_temp_date, highest_temp = get_highest_temp(max_dates, max_temps)
    lowest_temp_date, lowest_temp = get_lowest_temp(min_dates, min_temps)

*You are supposed to write a loop that finds the minimum and maximum yourself. You are not allowed to use built-in functions like `min()`, `max()`, `.sort()`, or `sorted()` for this exercise. There should also be no `print` statements within your `get_highest_temp()` and `get_lowest_temp()` functions.*

> **Making the problem smaller:** Verifying that your code determines the correct minimum and maximum values can be challenging when dealing with large temperature and date lists. However, one of the advantages of using functions is the ability to test them in isolation using some simple inputs, where you can easily verify and debug your solution.
>
> For this assignment, creating these simple tests would just require a list with some temperatures and a list with some dates. You can make these lists yourself, or slice them from the original larger list, as long as they are short enough that you can easily check the minimum/maximum yourself, and you can print all the steps of your function if needed.
>
> <details markdown="1"><summary  markdown="span"> *Click here for an example test:* </summary>
> You could test the `get_highest_temp` function using some straightforward test inputs:
>
    max_dates = ["day 1", "day 2", "day 3", "day 4"]
    max_temps = [12.5, -18.8, 19.2, 9.3]
    highest_temp_date, highest_temp = get_highest_temp(max_dates, max_temps)
    print(highest_temp_date, highest_temp)
    # Expected output:
    # day 3, 19.2
>
> Generally, it's wise to test functions with relatively small inputs where the expected output is easy to predict. Effective test cases can uncover potential programming errors. However, the mentioned example doesn't cover all possible scenarios. Even if this test produces the expected outcome, there could still be underlying issues in your code. The key is to devise test cases that are both straightforward and capable of revealing programming errors. Experiment with various edge cases your code might encounter, such as when the maximum value is the first or last element in the list. This approach helps ensure your code functions correctly in all scenarios, not just the initial simple test.
> </details>

Make sure your program calls the functions as above, and then *afterwards* `print`s the dates properly to the screen. For this you should **not** print:

     Max 34.5 at 19670513

but instead write out the entire month, so something like:

     The highest temperature was 34.5 degrees Celsius and was measured on 13 may 1967.

***Tip:*** Make a separate function that takes a number like `19670513` and converts it into a more readable expression like `13 may 1967`. Make use of functions in a logical way! As always, start by making the problem smaller and test your functions with just one simple input first.

<details markdown="1"><summary  markdown="span"> **Extra challenge:** </summary> If you need an extra challenge, find a way to reduce your duplicate code; the code that finds the minimum temperature and its date shouldn't be too different from the code that finds the maximum temperature and its date. Create a third function that can find both the maximum and minimum temperature depending on its inputs; you should only need one extra function argument for this. Call this function in `get_highest_temp()` and `get_lowest_temp()`. _This extra challenge is not a required part of the exercise._
</details>


## Testing

    checkpy weather2