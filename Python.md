I am using [roadmap.sh](http://roadmap.sh) for this section, i for the most part know the python essentials such as variables and that kinda stuff.

The [[Data Science]] part is linked here.
## Conditionals

### If else statement flowchart

This visualises how if statements work

```python
if expression
 Statement
else 
 Statement
```

### Inline if statement

```python
if <expr>: <statement_1>; <statement_2>; ...; <statement_n>
```

### Minimalistic if else

`A If B else C`. An example is shown below.

```python
def main():
	x,y = 10,8
	st = "x is less than y" if (x < y) else "x is greater than or equal to y"
	print(st)
	
if __name__ == "__main__":
	main()
```

### Switch case

```python
match term:
    case pattern-1:
         action-1
    case pattern-2:
         action-2
    case pattern-3:
         action-3
    case _:
        action-default
```

Python 3.10 onwards has an equivalent of the switch which is the match. This is an example of how you could implement it as a function

```python
date = input("Please enter your letter here: ")

def function(date):
    match date:
        case "M":
            return ("The date is Monday")
        case "T":
            return ("The date is Tuesday")
        case _: ## This is the default case
            return ("Its a weekend, have a dayoff")

def main():
    print(function("M"))

if __name__=='__main__':
    main()
```

The above code takes an input which it then parses to the function. The function then “matches the case”. Its like an if else

The dictionary match case also works

```python
def SwitchExample(argument):
    switcher = {
        0: " This is Case Zero ",
        1: " This is Case One ",
        2: " This is Case Two ",
    }
    return switcher.get(argument, "nothing")

if __name__ == "__main__":
    argument = 1
    print (SwitchExample(argument))
```
In this scenario the "nothing" in the return statement is the default case.

## Type Casting
Implicit type casting occurs when Python automatically converts one data type to another data type. For example, when you add an integer and a float, the integer gets implicitly converted to a float before the addition takes place.

Explicit type casting occurs when you manually convert one data type to another data type using a built-in function. For example, you can convert an integer to a string using the `str()` function.

Explicit type casting:
```python
#Explicit type casting
num_int = 123  # integer type
num_str = str(num_int)  # string type

print("datatype of num_int:",type(num_int))
print("datatype of num_str:",type(num_str))

```

## Raising an Exception
We can use `raise` to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

If you want to throw an error when a certain condition occurs using `raise`, you could go about it like this:

```python
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:

```bash
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

The program comes to a halt and displays our exception to screen, offering clues about what went wrong.

## The `AssertionError` Exception
Instead of waiting for a program to crash midway, you can also start by [making an assertion in Python](https://dbader.org/blog/python-assert-tutorial). We `assert` that a certain condition is met. If this condition turns out to be `True`, then that is excellent! The program can continue. If the condition turns out to be `False`, you can have the program throw an `AssertionError` exception.

```python
import sys
assert ('linux' in sys.platform), "This code runs on Linux only."
```

![Assertion error](assertion_error.png)

## The `try` and `except` Block: Handling Exceptions

The `try` and `except` block in Python is used to catch and handle exceptions. Python executes code following the `try` statement as a “normal” part of the program. The code that follows the `except` statement is the program’s response to any exceptions in the preceding `try` clause.

```python
try:
	#do something
except:
	#do this when an error occurs
```

In order to see exactly what went wrong, you would need to catch the error that the function threw.

The following code is an example where you capture the `AssertionError` and output that message to screen:

```python
try:
    linux_interaction()
except AssertionError as error:
    print(error)
    print('The linux_interaction() function was not executed')
```

Running this function on a Windows machine outputs the following:

```bash
Function can only run on Linux systems.
The linux_interaction() function was not executed
```

## The `else` Clause

In Python, using the `else` statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.

## Cleaning Up After Using `finally`
Imagine that you always had to implement some sort of action to clean up after executing your code. Python enables you to do so using the `finally` clause.
![Untitled](try_except_else_finally.png)
```python
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print('Cleaning up, irrespective of any exceptions.')
```
In the previous code, everything in the `finally` clause will be executed. It does not matter if you encounter an exception somewhere in the `try` or `else` clauses. Running the previous code on a Windows machine would output the following:
```bash
Function can only run on Linux systems.
Cleaning up, irrespective of any exceptions.
```
# Functions
```python
def my_func(*args): #*args means a list input
	# do something ...
	return # something
# setting an argument with a value gives it a default value
def my_other_func(**kwargs, name = "txddy-p"): ## **kwargs :dictionary input
	# do something
	return #something or nothing

def my_fxn(name: str, age: int): # here you can set the argument type
# I played around with this and it seems like it might be for debugging purposes
	# do something
	return #something or nothing
```
For the last function `name: str` this doesn't throw errors when you mess up the data type but could cause problems later.
### Docstring
The first string after the function is called the Document string or [Docstring](https://www.geeksforgeeks.org/python-docstrings/) in short. This is used to describe the functionality of the function. The use of docstring in functions is optional but it is considered a good practice.
### Nested Functions
functions can be nested, this is done in order to protect them from everything happening outside
More research needed here
### Built in functions
I'd say the more you use them the more you'll remember them.
# Lists, Tuples, Sets, Dictionaries
All of them are mutable except tuples
### Applications of List, Set, Tuple, and Dictionary
**List:**
- Used in JSON format
- Useful for Array operations
- Used in Databases
**Tuple:**
- Used to insert records in the database through SQL query at a time.Ex: (1.’sravan’, 34).(2.’geek’, 35)
- Used in parentheses checker
**Set:**
- Finding unique elements
- Join operations
**Dictionary:**
- Used to create a data frame with lists
- Used in JSON
So basically a set uses hashtables as its underlying data structure.
# Collections Counter
can be quickly used to convert a list with repeating items into a dictionary. Seems a very useful module so look into it
```python
from collections import Counter
dict(Counter(list))
```
# [[Data Structures and Algorythims]]
# [[RegEx]]
# [[Iterators]]
# [[Decorators]]
