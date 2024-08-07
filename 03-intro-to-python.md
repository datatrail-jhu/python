
# Intro to Python

Python is a popular programming language that was created by Guido van Rossum and released in 1991. 

Python is supported by multiple libraries that support data science tasks:

- [NumPy](https://numpy.org/) for numerical computing with multidimensional arrays.
- [pandas](https://pandas.pydata.org/) for data manipulation and analysis with data frames.
- [Matplotlib](https://matplotlib.org/) for data visualization.

## Main Differences between R and Python

| Feature                   | Python                                                                         | R                                                                                |
|---------------------------|--------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| Purpose                   | General-purpose programming language                                           | Statistical programming language                                                 |
| Suitability               | Good at multiple things, including machine learning and deep learning          | Very good at statistical analysis but less versatile for other tasks             |
| Key Libraries             | [TensorFlow](https://www.tensorflow.org/), [PyTorch](https://pytorch.org/), [scikit-learn](https://scikit-learn.org/stable/) | Primarily statistical and visualization libraries (not specified in the text)    |
| Tool for Sharing          | Jupyter Notebooks: Open source web application for sharing documents with live Python code, equations, visualizations, and explanations | Same as Python, as Jupyter Notebooks support both Python and R                    |



## Learning Objectives

```markdown
![alternative if the image is broken](https://docs.google.com/presentation/d/1k8uC1rqnGTSbKjBsWvKYgiUUxO1q_VhJCwZQHJNWozA/export/png?pageid=g29054a882fd_0_52)
```


## Python Syntax for R Users

An important difference in syntax is 0-based indexing for Python and 1-based indexing for R. This means that in R, indexing starts with 1 and in Python, indexing starts with 0. Coming from R, this means you have to subtract your "R indexes" by 1 to get the correct index in Python.

Other major differences in Python:

### Whitespace

Important in Python. In R, expressions are grouped into a code block with `{}`. In Python, expressions are grouped by indentation level. 

For example, in R, an if statement looks like:

```{r}
x <- 1

if (x > 0) {
    print("x is positive")
} else {
    print("x is negative")
}
```

In Python, the equivalent if statement looks like:

```python
x = 1

if x > 0:
    print("x is positive")
else:
    print("x is negative")
```


### Data Structures

There are 4 different data storage formats, or data structures, in Python: lists, tuples, dictionaries, and sets

#### Lists

Python lists are created using brackets `[]`. You can add elements to the list through the `append()` method.

```python
x = [1, 2, 3]
x.append(4) # add 4 to the end of list

print("x is", x)
#> x is [1, 2, 3, 4]
```


You can index into lists with integers using brackets `[]`, but note that indexing is 0-based.

```python
x = [1, 2, 3]

x[0]
#> 1
x[1]
#> 2
x[2]
#> 3
```


Negative numbers count from the end of the list.

```python
x = [1, 2, 3]

x[-1]
#> 3
x[-2]
#> 2
x[-3]
#> 1
```

You can slice ranges of lists using the : inside brackets. Note that the slice syntax is not inclusive of the end of the slice range.

```python
x = [1, 2, 3, 4, 5, 6]
x[0:2] # get items at index positions 0, 1
#> [1, 2]
x[1:]  # get items from index position 1 to the end
#> [2, 3, 4, 5, 6]
x[:-2] # get items from beginning up to the 2nd to last.
#> [1, 2, 3, 4]
x[:]   # get all the items
#> [1, 2, 3, 4, 5, 6]
```


#### Tuples

Tuples behave like lists, but are constructed using `()`, instead of `[]`. 

```python
x = (1, 2) # tuple of length 2
type(x)
#> <class 'tuple'>
len(x)
#> 2
x
#> (1, 2)

x = (1,) # tuple of length 1
type(x)
#> <class 'tuple'>
len(x)
#> 1
x
#> (1,)

x = 1, 2 # also a tuple
type(x)
#> <class 'tuple'>
len(x)
#> 2

x = 1, # beware a single trailing comma! This is a tuple!
type(x)
#> <class 'tuple'>
len(x)
#> 1
```

#### Dictionaries

Dictionaries are data structures where you can retrieve items by name. They can be created using syntax like `{key: value}`.

```python
d = {"key1": 1,
     "key2": 2}

d["key1"] 
#> 1
d["key3"] = 3
d 
#> {'key1': 1, 'key2': 2, 'key3': 3}
```

#### Sets 

Sets are used to track unique items, and can be constructed using `{val1, val2}`.

```python
s = {1, 2, 3}

type(s)
#> <class 'set'>
s
#> {1, 2, 3}
```

### Iteration with for loops
 
The `for` statement in Python is similar to the `for` loop in R. It can be used to iterate over any kind of data structure.

```python
for x in [1, 2, 3]:
  print(x)
#> 1
#> 2
#> 3
```

### Functions

Python functions are defined with the `def` statement. The syntax for specifying function arguments and default values is very similar to R.

```python
def my_function(name = "World"):
  print("Hello", name)

my_function()
#> Hello World
my_function("Friend")
#> Hello Friend
```

The equivalent R code would be

```{r}
my_function <- function(name = "World") {
  cat("Hello", name, "\n")
}

my_function()
#> Hello World
my_function("Friend")
#> Hello Friend
```


### Importing modules

In R, authors can bundle their code into R packages, and R users can access objects from R packages via `library()` or `::`. In Python, authors bundle code into modules, and users access modules using `import`.

```python
import numpy
```

Once loaded, you can access symbols from the module using `.`, which is equivalent to `::` in R.

```python
numpy.abs(-1)
```

There is special syntax for conveniently bounding a module to a symbol upon importing.

```python
import numpy        # import
import numpy as np  # import and bind to a custom symbol `np`

from numpy import abs # import only `numpy.abs`
from numpy import abs as abs2 # import only `numpy.abs`, bind it to `abs2`
```

### Learning More

If you want to learn more, browse the [official documentation for Python](https://docs.Python.org/3/).

### References 

- https://rstudio.github.io/reticulate/articles/python_primer.html
- https://www.youtube.com/watch?v=m_MQYyJpIjg

