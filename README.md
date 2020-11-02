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

I first calculated the square root of two to one hundred decimal places and printed it out. But when it was printed out the value was a big number with no decimal places. In order to add a decimal place the number had to be converted into a list and the . could be inserted then. The list is then joined together and printed out as a string.

<br />

$$ z_{next} = z - \frac{z^2 -x}{2z} $$

<br /> <br />

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
