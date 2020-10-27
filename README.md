# Emerging Technology


Introduction
-------------------------------------------------------------------------------------------------------------------

This Jupyter Notebook contains the tasks for the module "Emerging Tech" in 4th year Software Development Course. It is written in the Python programming language. It will contain the programs for the four different tasks that we will be given. 

The first task is: 

``` 
Write a Python function called sqrt2 that calculates and
prints to the screen the square root of 2 to 100 decimal places. Your code should
not depend on any module from the standard library1 or otherwise.
```


Task One
-------------------------------------------------------------------------------------------------------------------

According to the Oxford Dictionary a square root is a "a number which produces a specified quantity when multiplied by itself". All real numbers have two square roots, One positive and one negative.All square roots are written with the √ symbol. There are many ways to determine the the square root of a number. I will be discussing one of these methods and then trying to code a program that will be able to get the square root of a specified number and print it out to 100 decimal places.

One of the ways we can calculate the square root of a number is by using Newton's Method.[1,2,3]. Newton's Method uses a specific formula, seen below, to calculate the square root. It is known an an iterative method and approximates roots of equations. The algorithm starts off by guessing the square root of the given number as x > 0. It then computes a more accurate guess by taking the derivative of f(x) to get f'(x) and plug it into the formula. We then repeat the formula until we get a better and more accurate guess.

<br />

$$ z_{next} = z - \frac{z^2 -x}{2z} $$

<br /> <br />