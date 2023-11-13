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

# RegEx
Let's start with use-cases because I couldn't get myself into this. Remember that password generator you wanted to make, instead of having a dictionary or list to keep track of all the characters you can just use RegEx with a pattern. I take it you're sold now hey???

```python
import re #must be imported to be used
re.match(pattern, string, flags=0) # pattern is the thing you're looking for
```

The re.search() method takes a regular expression pattern and a string and searches for that pattern within the string. If the search is successful, search() returns a match object or None otherwise. Therefore, the search is usually immediately followed by an if-statement to test if the search succeeded, as shown in the following example which searches for the pattern 'word:' followed by a 3 letter word (details below):

#### `|` character
can be used to present a choice in terms of a regex. `love|like` will match `I love lemonade` or `I like lemonade`

#### `[cat]`
the regex `[cat]` will match each of the letters c, a and t but not the word cat

### Wild cards
#### `.`
will match any character. `\.` is used to match an actual period.

#### Ranges `[a-d]`
`[a-d]`. (This is purely conjecture) This syntax can be used to choose characters in a certain range. `[a-c]` would match the characters a,b,c and is equivalent to `[abc]`.
- `[A-Z]` specifies the uppercase letters. You can also add ranges together e.g. `[A-Za-z]` matches both upper and lowercase letters.
- `[0-9]` is digits

#### Short hand characters
- `\w`: the “word character” class represents the regex range `[A-Za-z0-9_]`, and it matches a single uppercase character, lowercase character, digit or underscore
- `\d`: the “digit character” class represents the regex range `[0-9]`, and it matches a single digit character
- `\s`: the “whitespace character” class represents the regex range `[ \t\r\n\f\v]`, matching a single space, tab, carriage return, line break, form feed, or vertical tab
- `\W`: the “non-word character” class represents the regex range `[^A-Za-z0-9_]`, matching any character that is not included in the range represented by `\w`
- `\D`: the “non-digit character” class represents the regex range `[^0-9]`, matching any character that is not included in the range represented by `\d`
- `\S`: the “non-whitespace character” class represents the regex range `[^ \t\r\n\f\v]`, matching any character that is not included in the range represented by `\s`

## Grouping

Remember when we were in love with baboons and gorillas a few exercises ago? We were able to match either `baboons` or `gorillas` using the regex `baboons|gorillas`, taking advantage of the `|` symbol.

But what if we want to match the whole piece of text `I love baboons` and `I love gorillas` with the same regex? Your first guess might be to use the regex `I love baboons|gorillas`. This regex, while it would completely match the [string](https://www.codecademy.com/resources/docs/general/data-types/string) `I love baboons`, would not match `I love gorillas`, and would instead match `gorillas`. This is because the `|` symbol matches the _entire_ expression before or after itself.

Grouping to the rescue! **_Grouping_**, denoted with the open parenthesis `(` and the closing parenthesis `)`, lets us group parts of a regular expression together, and allows us to limit alternation to part of the regex.

The regex `I love (baboons|gorillas)` will match the text `I love` and _then_ match either `baboons` or `gorillas`, as the grouping limits the reach of the `|` to the text within the parentheses.

These groups are also called _capture groups_, as they have the power to select, or capture, a substring from our matched text.

## Quantifiers - Fixed

Here’s where things start to get really interesting. So far we have only matched text on a character by character basis. But instead of writing the regex `\w\w\w\w\w\w\s\w\w\w\w\w\w`, which would match 6 word characters, followed by a [whitespace](https://www.codecademy.com/resources/docs/general/whitespace) character, and then followed by more 6 word characters, such as in the text `rhesus monkey`, is there a better way to denote the quantity of characters we want to match?

The answer is yes, with the help of quantifiers! **_Fixed quantifiers_**, denoted with curly braces `{}`, let us indicate the exact quantity of a character we wish to match, or allow us to provide a quantity range to match on.

- `\w{3}` will match _exactly_ 3 word characters
- `\w{4,7}` will match _at minimum_ 4 word characters and _at maximum_ 7 word characters

The regex `roa{3}r` will match the characters `ro` followed by `3` `a`s, and then the character `r`, such as in the text `roaaar`. The regex `roa{3,7}r` will match the characters `ro` followed by _at least_ `3` `a`s and _at most_ `7` `a`s, followed by an `r`, matching the strings `roaaar`, `roaaaaar` and `roaaaaaaar`.

An important note is that quantifiers are considered to be _greedy_. This means that they will match the greatest quantity of characters they possibly can. For example, the regex `mo{2,4}` will match the text `moooo` in the [string](https://www.codecademy.com/resources/docs/general/data-types/string) `moooo`, and not return a match of `moo`, or `mooo`. This is because the fixed quantifier wants to match the largest [number](https://www.codecademy.com/resources/docs/general/data-types/number) of `o`s as possible, which is `4` in the string `moooo`.

## Quantifiers - Optional

You are working on a research project that summarizes the findings of primate behavioral scientists from around the world. Of particular interest to you are the scientists’ observations of humor in chimpanzees, so you whip up some regex to find all occurrences of the word `humor` in the documents you have collected. To your dismay, your regex misses the observations of amusement written by scientists hailing from British English speaking countries, where the spelling of the word is `humour`. Optional quantifiers to the rescue!

**_Optional quantifiers_**, indicated by the question mark `?`, allow us to indicate a character in a regex is optional, or can appear either `0` times or `1` time. For example, the regex `humou?r` matches the characters `humo`, then either `0` occurrences or `1` occurrence of the letter `u`, and finally the letter `r`. Note the `?` _only_ applies to the character directly before it.

With all quantifiers, we can take advantage of grouping to make even more advanced regexes. The regex `The monkey ate a (rotten )?banana` will completely match both `The monkey ate a rotten banana` and `The monkey ate a banana`.

Since the `?` is a metacharacter, you need to use the escape character in your regex in order to match a question mark `?` in a piece of text. The regex `Aren't owl monkeys beautiful\?` will thus completely match the text `Aren't owl monkeys beautiful?`.

## Quantifiers - 0 or More, 1 or More

In 1951, mathematician Stephen Cole Kleene developed a system to match patterns in written language with mathematical notation. This notation is now known as regular expressions!

In his honor, the next piece of [regular expressions](https://www.codecademy.com/resources/docs/general/regular-expressions) syntax we will learn is known as the Kleene star. The **_Kleene star_**, denoted with the asterisk `*`, is also a quantifier, and matches the preceding character `0` or more times. This means that the character doesn’t need to appear, can appear once, or can appear many many times.

The regex `meo*w` will match the characters `me`, followed by `0` or more `o`s, followed by a `w`. Thus the regex will match `mew`, `meow`, `meooow`, and `meoooooooooooow`.

Another useful quantifier is the **_Kleene plus_**, denoted by the plus `+`, which matches the preceding character `1` or more times.

The regex `meo+w` will match the characters `me`, followed by `1` or more `o`s, followed by a `w`. Thus the regex will match `meow`, `meooow`, and `meoooooooooooow`, but not match `mew`.

Like all the other metacharacters, in order to match the symbols `*` and `+`, you need to use the escape character in your regex. The regex `My cat is a \*` will completely match the text `My cat is a *`.

## Anchors

When writing [regular expressions](https://www.codecademy.com/resources/docs/general/regular-expressions), it’s useful to make the expression as specific as possible in order to ensure that we do not match unintended text. To aid in this mission of specificity, we can use the anchor metacharacters. The **_anchors_** hat `^` and dollar sign `$` are used to match text at the start and the end of a [string](https://www.codecademy.com/resources/docs/general/data-types/string), respectively.

The regex `^Monkeys: my mortal enemy$` will completely match the text `Monkeys: my mortal enemy` but not match `Spider Monkeys: my mortal enemy in the wild` or `Squirrel Monkeys: my mortal enemy in the wild`. The `^` ensures that the matched text begins with `Monkeys`, and the `$` ensures the matched text ends with `enemy`.

Without the anchor tags, the regex `Monkeys: my mortal enemy` will match the text `Monkeys: my mortal enemy` in both `Spider Monkeys: my mortal enemy in the wild` and `Squirrel Monkeys: my mortal enemy in the wild`.

Once again, as with all other metacharacters, in order to match the symbols `^` and `$`, you need to use the escape character in your regex. The regex `My spider monkey has \$10\^6 in the bank` will completely match the text `My spider monkey has $10^6 in the bank`.

Python Regular Expression Quick Guide

^        Matches the beginning of a line
$        Matches the end of the line
.        Matches any character
`\s`                   Matches whitespace
`\S`                   Matches any non-whitespace character
`*`                     Repeats a character zero or more times
`*?`                     Repeats a character zero or more times  (non-greedy)
`+`                     Repeats a character one or more times
`+?`                   Repeats a character one or more times (non-greedy)
`[aeiou]`        Matches a single character in the listed set
`[^XYZ] `              Matches a single character not in the listed set
`[a-z0-9]`     The set of characters can include a range
(                     Indicates where string extraction is to start
)                     Indicates where string extraction is to end


Greedy matching just says whats the largest pattern that matches your pattern.

```bash
#Greedy matching
>>> import re
>>> x = 'From: Using the : character'
>>> y = re.findall('^F.+:', x)
>>> print(y)
['From: Using the :']

#Non greedy matching
>>> import re
>>> x = 'From: Using the : character'
>>> y = re.findall('^F.+?:', x)
>>> print(y)
['From:']
```
`re.search()` returns a True/False depending on whether the string matches  the regular expression
If we actually want the matching strings to be extracted, we use `re.findall()`. This is a global flag in general RegEx

`@([^ ]*)` extracts non blank characters