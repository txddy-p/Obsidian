These are functions defined in a single line, they are multi argument single expression functions.
Examples
```python
x = lambda a,b,c:a+b+c
print(x(1,2,3))
-----------------------------------
6
-----------------------------------


x = lambda a,b:a*b
print(x(4,5))
-----------------------------------
20
-----------------------------------


x = lambda a:a+1
print(x(6))
-----------------------------------
7
-----------------------------------


# parsing arguments to a lambda function
(lambda x: x + 1)(2)
-----------------------------------
3
-----------------------------------
```