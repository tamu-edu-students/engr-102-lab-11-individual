# ENGR 102 Lab Topic 11 (individual)

## Activities
There are three deliverables for this individual assignment. Please submit the following files to Gradescope. Check out the [Frequently Asked Questions](#frequently-asked-questions) below. **Please include the individual header in your ~.py file.**

1. [Barcode Checker](#barcode-checker)
2. [Loan Calculator](#loan-calculator)
3. [Weather Data](#weather-data)

## Barcode Checker
This 

## Loan Calculator
stuff

## Weather Data
more stuff

## Frequently Asked Questions
1. **I downloaded the `barcodes.txt` / `WeatherDataCLL.csv` file and tried to run my code, but I get the error "No such file or directory". What does that mean?** Please see [the FAQ for Lab: Topic 11 (team)](https://github.com/tamu-edu-students/engr-102-lab-11-team?tab=readme-ov-file#frequently-asked-questions) for help on this.

2. **I can't get my code to pass the "file created correctly" test case. Should I be worried?** YES. This activity is completely autograded. If you want the points, you need to create the file correctly.

3. **Do I need to submit my `valid_barcodes.txt` and `out.csv` files?** Nope! The autograding code on Gradescope will run your submitted python files, create the output files that your code (should) generate, then check them. If you submit them, they will just be ignored.

4. **Activity 1 (barcode checker) do you have a better way to explain the barcode math?** Yes! Here is a nice poster with color coded numbers to make it easier to understand.

5. **Activity 2 (loan calculator) my numbers are off! Help!** Try solving the problem by hand. Okay, not the whole problem, just two or three months. Write down ALL of your steps, don't leave out obvious or easy things that you can do in your head. Make sure your steps are in order (remember sequence of steps?). Now, where do your calculations start to repeat? Does your code perform those same calculations in the same order? Also, total accrued interest is the running total of each month's accrued interest up to that point. And the ending balance of one month is the beginning balance of the next month.

6. **Activity 2 (loan calculator) I have $-0.00 instead of $0.00 on the last line of my generated file. How do I fix it?** If that's the only thing off in your generated file, that's pretty good! To fix it, add some code to detect if the value is negative, then set it equal to zero.

7. **Activity 3 (weather data) why is this so hard?! Any advice?** More students struggle with this particular activity than any other activity in this class. First, you need to read the file, then process the data into something useable. Think about how you want to organize the data. Do you want to store each day (row) in its own list? Or maybe make a list for each category (column)? Dying to try out dictionaries? This is a great problem to use them! There are multiple ways to organize the data, so choose something that makes sense to you. Once you have the data processed, then it's a matter of looping through it and extracting the values you need to perform the calculations required. Here's a hint: remember the lecture slide about splitting a date string? That's pretty useful for figuring out if a particular date is in the month and year input by the user...

Have a question you don't see here? Email your instructor!

Revised Fall 2025 SNR
