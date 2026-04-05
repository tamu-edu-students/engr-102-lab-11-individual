# ENGR 102 Lab Topic 11 (individual)

## Activities
There are three deliverables for this individual assignment. Please submit the following files to Gradescope. Check out the [Frequently Asked Questions](#frequently-asked-questions) below. **Please include the individual header in your ~.py file.** These activities are meant to help give you practice reading and writing files, as well as processing larger amounts of data, which is one of the common tasks that computer programs are written for.

1. [Barcode Checker](#barcode-checker)
2. [Loan Calculator](#loan-calculator)
3. [Weather Data](#weather-data)

## Barcode Checker
A barcode is valid if the digits satisfy a certain constraint. For example, take the 13-digit barcode `1877455846014` and split the first 12 digits into two groups: `(1,7,4,5,4,0)` and `(8,7,5,8,6,1)`. The first group contains every other digit starting with the first, and the second group contains every other digit starting with the second. Take the sum of the digits in the second group and multiply it by 3. Add to that the sum of the digits in the first group. Subtract the last digit of that number from 10, and it should match the last digit of the barcode. Note: if the last digit is zero, the barcode should end in zero.

Example math using barcode `1877455846014`:</br>
Sum of first group = 1 + 7 + 4 + 5 + 4 + 0 = **21**</br>
Sum of second group = 8 + 7 + 5 + 8 + 6 + 1 = **35**</br>
Multiply second group by 3 = **35** x 3 = 105</br>
Add first group = 105 + **21** = 12**6**</br>
Use the last digit and subtract from ten = 10 - **6** = 4</br>
4 is the last digit in the barcode, so it is valid

Write a program named `barcode_checker.py` that takes as input a filename (like [barcodes.txt](barcodes.txt)) that contains many 13-digit barcodes. Have your program read the file, determine whether each barcode is valid, and write the valid barcodes to a new file named `valid_barcodes.txt`. Have your program output the total number of valid barcodes found using the example output below. You do not have to submit your `valid_barcodes.txt` file to Gradescope.

Example output using `barcodes.txt`:
```
Enter the name of the file: barcodes.txt
There are ?? valid barcodes
```


## Loan Calculator
This activity provides practice with CSV (Comma Separated Value) files. CSV files are one of the most common formats for storing tabular data (e.g. spreadsheets). Each line represents a row of the table, and the cells in each column are separated by commas. CSV files can usually be read by spreadsheet programs (such as Microsoft Excel), and most spreadsheet programs can output their data in the CSV format. These files are often given the ~.csv extension. In this activity, you will practice reading and writing data in the CSV format using Python.

Write a program named `loan_calculator.py` that will write to a file a list of amortized values for a loan. Have your program take as input from the user the output filename, the principal amount of the loan ($$P$$), the number of months over which the loan will be repaid ($$N$$), and the annual interest rate ($$i$$). Note that $$i$$ should be a decimal number, not a percentage: 0.025 instead of 2.5%. Calculate the monthly payment ($$M$$) as:

$$M=\frac{Pi/12}{1-(\frac{1}{1+i/12})^N}$$

For the example below, $$M$$=$1774.74. Create an output file using the filename obtained from the user, and in the first line write the header as shown in the example below. After the header, write to the file the initial values for the month number, the total amount of interest accrued so far using 2 decimal places, and the amount remaining on the loan using 2 decimal places. For each month starting with month 1 and ending when the balance is less than $0.01, perform the following calculations:

- The monthly accrued interest: multiply the balance at the beginning of the month by $$i⁄12$$
- The balance at the end of the month: add the accrued interest to the beginning balance and subtract the monthly payment
- The total interest accrued: add the current monthly interest to all previous months

**Note:** If you write your CSV file correctly, you should be able to open it in a spreadsheet program that can read CSV files (like Excel). You can also check your values using the `PMT()` function in Excel:
`PMT(0.025/12, 60, 100000) = ($1774.74)`

Example output (using inputs `out.csv`, `100000`, `60`, `0.025`):
```
Enter the output filename: out.csv
Enter the principal amount: 100000
Enter the term length (months): 60
Enter the annual interest rate: 0.025
```

Example file created by your program:
```
Month,Total Accrued Interest,Loan Balance
0,$0.00,$100000.00
1,$208.33,$98433.60
...
59,$6480.48,$1771.05
60,$6484.17,$0.00
```


## Weather Data
The [CSV file posted with this assignment](WeatherDataCLL.csv) named `WeatherDataCLL.csv` contains weather data from Easterwood Airport (in College Station) for 10 years. The data was taken from the National Oceanic and Atmospheric Administration’s National Centers for Environmental Information (NOAA’s NCEI, https://www.ncdc.noaa.gov/). You can view the data by opening the file in any text or spreadsheet editor (e.g. Notepad++, Excel) or in your IDE. The first line of the file contains the column headers explaining what each column is. **Note:** Some days are missing data.

Download the file and write a program named `weather_data.py` that does the following:
1.	Open the CSV file for reading
2.	Read the CSV file and compute
    <ul>
    <li>the maximum temperature seen over the 10-year period</li>
    <li>the minimum temperature seen over the 10-year period</li></ul>
4.	Output the results to the console using the format below
5.	Perform the following seven data analysis exercises and output the results to the console. Take as input from the user a month and year, then for that month,
    <ul><li>Calculate the mean of the average pressure (use 2 decimal places)</li>
    <li>Calculate the mean of the average temperature (use 1 decimal place)</li>
    <li>Calculate the mean of the average wet bulb temperature (use 1 decimal place)</li>
    <li>Calculate the mean of the average dew point (use 1 decimal place)</li>
    <li>Calculate the mean of the average relative humidity (use 1 decimal place)</li>
    <li>Calculate the mean of the average daily wind speed (use 2 decimal places)</li>
    <li>Calculate the percentage of days with non-zero precipitation (use 1 decimal place)</li></ul>

Example Output (using inputs `July`, `2024`, but with made-up numbers):
```
10-year maximum temperature: 102 F
10-year minimum temperature: 7 F

Please enter a month: July
Please enter a year: 2024

For July 2024:
Mean average daily pressure: 29.73 in Hg
Mean average daily temperature: 92.5 F
Mean average daily wet bulb temperature: 81.2 F
Mean average daily dew point: 78.1 F
Mean average daily relative humidity: 58.6%
Mean average daily wind speed: 7.34 mph
Percentage of days with precipitation: 2.1%
```



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
