# Emerging Technology


Introduction
-------------------------------------------------------------------------------------------------------------------

This Jupyter Notebook contains the tasks for the module "Emerging Technology" in 4th year Software Development Course. It is written in the Python programming language. It will contain the programs for the four different tasks that we will be given.

This README gives a brief description and information about each task but the full code and the research used can be found in the jupyter notebook in this repository. This README will also demonstrate how to run this repository using cmd or cmder.

The four tasks are as follow:

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

The third task is: 

```
The standard deviation of an array of numbers x is calculated using numpy as np.sqrt(np.sum((x - np.mean(x))**2)/len(x)). 
However, Microsoft Excel has two different versions of the standard deviation calculation, STDDEV.P and STDDEV.S . 
The STDDEV.P function performs the above calculation but in the STDDEV.S calculation the division is by len(x)-1 
rather than len(x) . Research these Excel functions, writing a note in a Markdown cell about the difference between 
them. Then use numpy to perform a simulation demonstrating that the STDDEV.S calculation is a better estimate for 
the standard deviation of a population when performed on a sample. Note that part of this task is to figure out 
the terminology in the previous sentence.
```

The fourth task is: 

```
Use scikit-learn to apply k-means clustering to Fisher’s famous Iris data set. 
You will easily obtain a copy of the data set online. Explain in a Markdown cell 
how your code works and how accurate it might be, and then explain how your model 
could be used to make predictions of species of iris. 
```


Task One
-------------------------------------------------------------------------------------------------------------------
#### Task: Calculate the square root of 2 to one hundred decimal places
---------------------------------------------------------------------

According to the Oxford Dictionary a square root is a "a number which produces a specified quantity when multiplied by itself". All real numbers have two square roots, One positive and one negative. All square roots are written with the √ symbol. There are many ways to determine the the square root of a number. I will be discussing one of these methods and then trying to code a program that will be able to get the square root of a specified number and print it out to 100 decimal places.

There are many ways that we can calculate the square root of 2 such as Newthon's Method and Eular's Method. All these methods are very efficient and good at getting the square root of 2 but they sometimes cannot print the value to 100 places. FOr example, Newthons method is only able to print out the values to 52 places.  I used a different formula to calculate the square root of 2 to 100 places. This formula uses a googol which is the largest number in the world and a while loop to estimate the answer. The code and research for this task can be found in the jupyter notebook.


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

I originally had the code that it would use the panda library to create a dataframe using the the relevant values and output the result. The table that was printed was very similar to the one shown above. The table and the values were saved in a variable called "data", which woud be used later by the scipy.stats library. I then realised that I was only meant to use the scipy.stats library to perform the required calculations. I decided to change the code a little bit to better fit the requirements. I did this by creating a variable and adding the dataset from the table into it. The dataset was saved row by row: 

```
#data to be inserted into the columns
data = [[90,60,104,95], [30,50,51,20],[30,40,45,35]]
```

The data is then used to get the four values printed out by the stats.chi2_contingency(data) method. These four values are the chi squared values, the p value, the degrees of freedom and the expected frequencies. These values were then printed out and the chi squared value printed was the same as the one we were trying to verify.

```
chi2, p, dof, ex = stats.chi2_contingency(data)
```

The values that are printed are: 

```
The approximate chi squared value is: 24.6 

The associated p value is: 0.0004098425861096696 

The Degree of Freedom is: 6 

The expected frequencies are: 
 [[ 80.53846154  80.53846154 107.38461538  80.53846154]
 [ 34.84615385  34.84615385  46.46153846  34.84615385]
 [ 34.61538462  34.61538462  46.15384615  34.61538462]] 
 ```
 

Task Three
-------------------------------------------------------------------------------------------------------------------

#### Task: Research the excel functions and use numpy to perform a simulation demonstrating that the STDEV.S calculation is a better estimate for the standard deviation of a population when performed on a sample.
-------------------------------------------------------------------------------------------------------------------------------------------
In the task 3 part of the notebook I explain what the difference between STDDEV.S and STDDEV.P is and show why STDDEV.S is better for calculation is a better estimate for the standard deviation of a population when performed on a sample. I carried out a calculation to test this hypothesis and show that STDEV.S is better. 

The testing showed that the sample calculation formula works better on a sample of the population rather than the population formula. The two formuals are the following: 


```Population: np.sqrt(np.sum((x - np.mean(x)) ** 2)/len(x))```

And

``` Sample: np.sqrt(np.sum((x - np.mean(x)) ** 2)/len(x)) -1```

There is a slight difference in the population and sample formula but this allows the sample data to get a better mathematical estimate of the population. It statistically gives a better estimate than population due to it working with only a small sample than the entire population.


Task Four
-------------------------------------------------------------------------------------------------------------------

#### Task:  Use scikit-learn to apply k-means clustering to Fisher’s famous Iris data set.
-------------------------------------------------------------------------------------------------------------------------------------------

In task four we are required to use scikit-learn and apply k-means clustering to the famous Iris data set. The task starts off by explaining what the Iris data set is and what it is used for. After explaining the data set, we start the coding. We first import the different libraries and classes that we will be using. 

I then load the data from the scikit-learn datasets. The data is then plotted and the different values ae shown properly. The graph has names on both axis and there is also a title.


How to run
-------------------------------------------------------------------------------------------------------------------

In order to run these tasks please do the following:

Clone this repository:
```
git clone https://github.com/sagheerahmadGmit/EmergingTechTasks
```

After cloning, open up the terminal and type:
```
jupyter notebook
```

Open the tasks notebook and run the cells by either:
```
shift enter
```
or
```
press kernal at the top of the notebook and press "restart and run all
```


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

[6] Stats scipy library  
https://docs.scipy.org/doc/scipy/reference/stats.html  

[7] P value  
https://en.wikipedia.org/wiki/P-value  

#### Task: The difference between stdev.p and stdev.s
-------------------------------------------------------------------------------

[1]The difference between population and sample:   
[https://www.scribbr.com/methodology/population-vs-sample/  ]  
  
[2]Population vs Sample Data:  
[http://mathbitsnotebook.com/Algebra1/StatisticsData/STPopSample.html  ]  
    
[3]How to use stdev.p in excel:  
[https://www.exceltip.com/statistical-formulas/how-to-use-excel-stdev-p-function.html]  
  
[4]How to use stdev.s in excel:  
[https://www.exceltip.com/statistical-formulas/how-to-use-stdev-s-function-in-excel.html]  

#### Task: Use scikit-learn to apply k-means clustering to Fisher’s famous Iris data set.
-------------------------------------------------------------------------------
[1] Fishers Iris Dataset
[https://en.wikipedia.org/wiki/Iris_flower_data_set]  
  
[2] Scikit Learn - KMeans Clustering Analysis with the Iris Data Set  
[https://www.youtube.com/watch?v=asW8tp1qiFQ&ab_channel=DragonflyStatistics]  

[3] kmeans-examples.ipynb  
[https://github.com/ianmcloughlin/jupyter-teaching-notebooks/blob/master/kmeans-examples.ipynb]  
  
[4] Use Scikit Learn - K Means Clustering Analysis with the Iris Data Set  
[https://www.youtube.com/watch?v=I38fOLHC8zo&ab_channel=CodeCap]
