# Temperatures and freezing days per decade

Create a file called `weather6.py` and answer the question below.

### Assignment

* Write a program that plots both the average temperatures per decade (based on the daily maximum temperatures) and the amount of freezing days per decade in one single plot.
* Think how to create a combination of different plot styles to make both trends clearly visible.
* Use both y-axes using 

        fig, ax1 = plt.subplots()
        ax2 = ax1.twinx() 

