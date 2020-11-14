# Emerging Technology


Introduction
-------------------------------------------------------------------------------------------------------------------

This Jupyter Notebook contains the tasks for the module "Emerging Technology" in 4th year Software Development Course. It is written in the Python programming language. It will contain the programs for the four different tasks that we will be given. 

The first task is: 

``` 
Write a Python function called sqrt2 that calculates and
prints to the screen the square root of 2 to 100 decimal places. Your code should
not depend on any module from the standard library1 or otherwise.
```
The second task is :

```
The Chi-squared test for independence is a statistical
hypothesis test like a t-test. It is used to analyse whether two categorical variables
are independent. The Wikipedia article gives the table below as an example [4],
stating the Chi-squared value based on it is approximately 24.6. Use scipy.stats
to verify this value and calculate the associated p value. You should include a short
note with references justifying your analysis in a markdown cell.
```


Task One
-------------------------------------------------------------------------------------------------------------------
#### Task: Calculate the square root of 2 to one hundred decimal places
---------------------------------------------------------------------

According to the Oxford Dictionary a square root is a "a number which produces a specified quantity when multiplied by itself". All real numbers have two square roots, One positive and one negative. All square roots are written with the √ symbol. There are many ways to determine the the square root of a number. I will be discussing one of these methods and then trying to code a program that will be able to get the square root of a specified number and print it out to 100 decimal places.

One of the ways we can calculate the square root of a number is by using Newton's Method.[1,2,3]. Newton's Method uses a specific formula, seen below, to calculate the square root. It is known an an iterative method and approximates roots of equations. The algorithm starts off by guessing the square root of the given number as x > 0. It then computes a more accurate guess by taking the derivative of f(x) to get f'(x) and plug it into the formula. We then repeat the formula until we get a better and more accurate guess. The problem that I encountered with this formula was that it does not print out the value to 100 decimal places. It prints out the first 52 values and the rest are left as Zeros.

The formula shown below is another way of calculating the the square root of 2. The first thing the method is doing is setting the x value from the user to, x multiplied by 10 to the power of 200. This will take all the numbers from the right side of the decimal place and brings it to the left side. The method has 2 other variables, one is a variable used in the while loop while the other is a googol. The while loop keeps running until an accurate guess is made. Inside the while loop we are setting b to z and then calculating a better guess for z. The guess is using floor devision because we do not want any decimal places in the answer. The guess is also being bitshifted to the right, the bitshifting shifts the bits of the first operand right by the specified number of bits.[6] Once the guess is accurate the while loop stops and prints out the value. I first had it so the program prints the value z staright away but this was a problem because when it was printed out, the value was a big number with no decimal places. In order to add a decimal place the number had to be converted into a list and the . could be inserted then. The list is then joined together and printed out as a string.


Task Two
-------------------------------------------------------------------------------------------------------------------

#### Task: Use scipy.stats to verify this value and calculate the associated p value
-------------------------------------------------------------------------------

The Chi-squared test for independence is a statistical hypothesis test like a t-test. It is used to analyse whether two categorical variables are independent. The Wikipedia article in the research section, gives the table below as an example [1],
stating the Chi-squared value based on it is approximately 24.6. <br>

|             | A   | B   | C   | D   | Total  |
| ----------- | ----| ----| ----| ----|--------|
| White collar| 90  | 60  | 104 | 95  | 349    |
| Blue collar | 30  | 50  | 51  | 20  | 151    |
| No collar   | 30  | 40  | 45  | 35  | 150    |
| Total       | 150 | 150 | 200 | 150 | 650    |

<br><br>

The chi squared tests are used to check if there is a statistical difference between the expected and observed frequencies in a contigency table. It tests the association between the two criteria of association.  

The code below is verifying that the chi square value is correct and also prints out the p value. The code first creates a table with the data given and prints it out using the panda library.[2] The table that is printed is the same table as seen above. The data is stored in a variable named "data". We next use the scipy.stats library to figure out the Expected value, the p value, the actual chi square value and the degree of freedom. We use the  " stats.chi2_contingency(data)"[4] to get these values. This method returns all those values based on the marginal sums under the assumption of independence. The assumptions are:[3]

1. the observations are independent and
2. normally distributed


Research
-------------------------------------------------------------------------------------------------------------------
#### Task: Calculate the square root of 2 to one hundred decimal places
---------------------------------------------------------------------

[1] A tour of GO; Exercise: Loops and functions  
https://tour.golang.org/flowcontrol/8

[2] Newthon's Method  
https://en.wikipedia.org/wiki/Newton%27s_method

[3] Newthon's Method  
https://www.youtube.com/watch?v=E24zUEKqgwQ&ab_channel=OscarVeliz

[4] Calculating the square root of 2  
https://stackoverflow.com/questions/5187664/generating-digits-of-square-root-of-2

[5] Coverting a number to a list  
https://stackoverflow.com/questions/53976250/how-to-add-dot-separator-on-different-positions-of-a-number-in-python

[6] Bit Shifting  
https://www.tutorialspoint.com/python/bitwise_operators_example.htm

#### Task: Use scipy.stats to verify this value and calculate the associated p value
-------------------------------------------------------------------------------
[1] Chi Squared tests
https://en.wikipedia.org/w/index.php?title=Chi-squared_test&oldid=983024096  

[2] How to panda dataframes
https://datatofish.com/create-pandas-dataframe/  

[3] Chi squared tests
http://mmcmodinagar.ac.in/econtent/zoology/CHI_SQUARE_TESTS.pdf  

[4] Scipy.stats contigency
https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.chi2_contingency.html 

[5] The degrees of freedom  
https://en.wikipedia.org/wiki/Degrees_of_freedom_(statistics)  
