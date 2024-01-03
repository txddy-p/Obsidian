# Prerequisites
## Assigning Functions to Variables
```python
def plus_one(number):     
  return number + 1  
add_one = plus_one add_one(5)
```
- Functions can be assigned to variables, the variable then points to the same function
- The use cases I can think of are for generic functions like a multiply function being turned to a specific 'multiply by'
## Defining Functions Inside other Functions 
```python
def plus_one(number):
    def add_one(number):
        return number + 1


    result = add_one(number)
    return result
plus_one(4)
```
- Functions can also be defined inside another function but are limited to that function and cannot be called from outside that function. Nested functions can only be called directly by the function they are immediately nested inside
## Passing Functions as Arguments to other Functions
```python
def plus_one(number):
    return number + 1

def function_call(function):
    number_to_add = 5
    return function(number_to_add)

function_call(plus_one)
```
## Functions Returning other Functions
```python
def hello_function():
    def say_hi():
        return "Hi"
    return say_hi
hello = hello_function()
hello()
```
## Nested Functions have access to the Enclosing Function's Variable Scope
Python allows a nested function to access the outer scope of the enclosing function. This is a critical concept in decorators -- this pattern is known as a Closure.
```python
def print_message(message):
    "Enclosong Function"
    def message_sender():
        "Nested Function"
        print(message)

    message_sender()

print_message("Some random message")
```
# Creating Decorators
With these prerequisites out of the way, let's go ahead and create a simple decorator that will convert a sentence to uppercase. We do this by defining a wrapper inside an enclosed function. As you can see it very similar to the function inside another function that we created earlier.
```python
def uppercase_decorator(function):
    def wrapper():
        func = function()
        make_uppercase = func.upper()
        return make_uppercase
    return wrapper
```
Our decorator function takes a function as an argument, and we shall, therefore, define a function and pass it to our decorator. We learned earlier that we could assign a function to a variable. We'll use that trick to call our decorator function.
```python
def say_hi():
    return 'hello there'

decorate = uppercase_decorator(say_hi)
decorate()
```
However, Python provides a much easier way for us to apply decorators. We simply use the @ symbol before the function we'd like to decorate. Let's show that in practice below.
```python
@uppercase_decorator
def say_hi():
	return 'hello there'
say_hi()
```
## Applying Multiple Decorators to a Single Function
We can use multiple decorators to a single function. However, the decorators will be applied in the order that we've called them. Below we'll define another decorator that splits the sentence into a list. We'll then apply the `uppercase_decorator` and `split_string` decorator to a single function.

```python
def split_string(function):
    def wrapper():
        func = function()
        splitted_string = func.split()
        return splitted_string

    return wrapper

@split_string 
@uppercase_decorator 
def say_hi():
	return 'hello there'
say_hi()
```
```bash
#Output
['HELLO', 'THERE']
```
 From the above output, we notice that the application of decorators is from the bottom up. Had we interchanged the order, we'd have seen an error since lists don't have an `upper` attribute. The sentence has first been converted to uppercase and then split into a list.
## Accepting Arguments in Decorator Functions
Sometimes we might need to define a decorator that accepts arguments. We achieve this by passing the arguments to the wrapper function. The arguments will then be passed to the function that is being decorated at call time.
```python
def decorator_with_arguments(function):
    def wrapper_accepting_arguments(arg1, arg2):
        print("My arguments are: {0}, {1}".format(arg1,arg2))
        function(arg1, arg2)
    return wrapper_accepting_arguments


@decorator_with_arguments
def cities(city_one, city_two):
    print("Cities I love are {0} and {1}".format(city_one, city_two))

cities("Nairobi", "Accra")
```
```bash
# Output
My arguments are: Nairobi, Accra 
Cities I love are Nairobi and Accra
```
## Defining General Purpose Decorators
To define a general purpose decorator that can be applied to any function we use `args` and `**kwargs`. `args` and `**kwargs` collect all positional and keyword arguments and stores them in the args and kwargs variables. `args` and `kwargs` allow us to pass as many arguments as we would like during function calls.
```python
def a_decorator_passing_arbitrary_arguments(function_to_decorate):
    def a_wrapper_accepting_arbitrary_arguments(*args,**kwargs):
        print('The positional arguments are', args)
        print('The keyword arguments are', kwargs)
        function_to_decorate(*args)
    return a_wrapper_accepting_arbitrary_arguments

@a_decorator_passing_arbitrary_arguments
def function_with_no_argument():
    print("No arguments here.")

function_with_no_argument()
```
```bash
The positional arguments are ()
The keyword arguments are {}
No arguments here.
```
 Let's see how we'd use the decorator using positional arguments.
```python
@a_decorator_passing_arbitrary_arguments 
def function_with_arguments(a, b, c):
	print(a, b, c)  
function_with_arguments(1,2,3)`
```
```bash
The positional arguments are (1, 2, 3) 
The keyword arguments are {} 
1 2 3
```
 Keyword arguments are passed using keywords. An illustration of this is shown below.
```python
@a_decorator_passing_arbitrary_arguments 
def function_with_keyword_arguments():
	print("This has shown keyword arguments")  function_with_keyword_arguments(first_name="Derrick", last_name="Mwiti")
 ```
```bash
The positional arguments are () 
The keyword arguments are {'first_name': 'Derrick', 'last_name': 'Mwiti'} 
This has shown keyword arguments
```
## Passing Arguments to the Deorator
Now let's see how we'd pass arguments to the decorator itself. In order to achieve this, we define a decorator maker that accepts arguments then define a decorator inside it. We then define a wrapper function inside the decorator as we did earlier.
```python
def decorator_maker_with_arguments(decorator_arg1, decorator_arg2, decorator_arg3):
    def decorator(func):
        def wrapper(function_arg1, function_arg2, function_arg3) :
            "This is the wrapper function"
            print("The wrapper can access all the variables\n"
                  "\t- from the decorator maker: {0} {1} {2}\n"
                  "\t- from the function call: {3} {4} {5}\n"
                  "and pass them to the decorated function"
                  .format(decorator_arg1, decorator_arg2,decorator_arg3,
                          function_arg1, function_arg2,function_arg3))
            return func(function_arg1, function_arg2,function_arg3)

        return wrapper

    return decorator

pandas = "Pandas"
@decorator_maker_with_arguments(pandas, "Numpy","Scikit-learn")
def decorated_function_with_arguments(function_arg1, function_arg2,function_arg3):
    print("This is the decorated function and it only knows about its arguments: {0}"
           " {1}" " {2}".format(function_arg1, function_arg2,function_arg3))

decorated_function_with_arguments(pandas, "Science", "Tools")
```
```bash
 The wrapper can access all the variables
    - from the decorator maker: Pandas Numpy Scikit-learn
    - from the function call: Pandas Science Tools
and pass them to the decorated function
This is the decorated function, and it only knows about its arguments: Pandas Science Tools
```
## Debugging Decorators
As we have noticed, decorators wrap functions. The original function name, its docstring, and parameter list are all hidden by the wrapper closure: For example, when we try to access the `decorated_function_with_arguments` metadata, we'll see the wrapper closure's metadata. This presents a challenge when debugging.
```python
decorated_function_with_arguments.__name__
'wrapper'
decorated_function_with_arguments.__doc__
'This is the wrapper function'
```
In order to solve this challenge Python provides a `functools.wraps` [decorator](https://docs.python.org/3/library/functools.html#functools.wraps). This decorator copies the lost metadata from the undecorated function to the decorated closure. Let's show how we'd do that.
```python
import functools

def uppercase_decorator(func):
    @functools.wraps(func)
    def wrapper():
        return func().upper()
    return wrapper

@uppercase_decorator
def say_hi():
    "This will say hi"
    return 'hello there'

say_hi()
```
```bash
'HELLO THERE'`
```
When we check the `say_hi` metadata, we notice that it is now referring to the function's metadata and not the wrapper's metadata.
```python
say_hi.__name__`
--------------------------------------------------------------
'say_hi'
```
```python
say_hi.__doc__
--------------------------------------------------------------
'This will say hi'
```
 It is advisable and good practice to always use `functools.wraps` when defining decorators. It will save you a lot of headache in debugging.
## Python Decorators Summary
Decorators dynamically alter the functionality of a function, method, or class without having to directly use subclasses or change the source code of the function being decorated. Using decorators in Python also ensures that your code is DRY(Don't Repeat Yourself). Decorators have several use cases such as:
- Authorization in Python frameworks such as Flask and Django
- Logging
- Measuring execution time
- Synchronization