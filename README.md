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

According to the Oxford Dictionary a square root is a "a number which produces a specified quantity when multiplied by itself". All real numbers have two square roots, One positive and one negative. All square roots are written with the √ symbol. There are many ways to determine the the square root of a number. I will be discussing one of these methods and then trying to code a program that will be able to get the square root of a specified number and print it out to 100 decimal places.

One of the ways we can calculate the square root of a number is by using Newton's Method.[1,2,3]. Newton's Method uses a specific formula, seen below, to calculate the square root. It is known an an iterative method and approximates roots of equations. The algorithm starts off by guessing the square root of the given number as x > 0. It then computes a more accurate guess by taking the derivative of f(x) to get f'(x) and plug it into the formula. We then repeat the formula until we get a better and more accurate guess. The problem that I encountered with this formula was that it does not print out the value to 100 decimal places. It prints out the first 52 values and the rest are left as Zeros.

The formula shown below is another way of calculating the the square root of 2. The first thing the method is doing is setting the x value from the user to, x multiplied by 10 to the power of 200. This will take all the numbers from the right side of the decimal place and brings it to the left side. The method has 2 other variables, one is a variable used in the while loop while the other is a googol. The while loop keeps running until an accurate guess is made. Inside the while loop we are setting b to z and then calculating a better guess for z. The guess is using floor devision because we do not want any decimal places in the answer. The guess is also being bitshifted to the right, the bitshifting shifts the bits of the first operand right by the specified number of bits.[6] Once the guess is accurate the while loop stops and prints out the value. I first had it so the program prints the value z staright away but this was a problem because when it was printed out, the value was a big number with no decimal places. In order to add a decimal place the number had to be converted into a list and the . could be inserted then. The list is then joined together and printed out as a string.


<br /> <br />

Task Two
-------------------------------------------------------------------------------------------------------------------

#### Task: Use scipy.stats to verify this value and calculate the associated p value
-------------------------------------------------------------------------------

The Chi-squared test for independence is a statistical hypothesis test like a t-test. It is used to analyse whether two categorical variables are independent. The Wikipedia article in the research section, gives the table below as an example [4],
stating the Chi-squared value based on it is approximately 24.6. <br>

|             | A   | B   | C   | D   | Total  |
| ----------- | ----| ----| ----| ----|--------|
| White collar| 90  | 60  | 104 | 95  | 349    |
| Blue collar | 30  | 50  | 51  | 20  | 151    |
| No collar   | 30  | 40  | 45  | 35  | 150    |
| Total       | 150 | 150 | 200 | 150 | 650    |

Research
-------------------------------------------------------------------------------------------------------------------

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
