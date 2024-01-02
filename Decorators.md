## Assigning Functions to Variables
```python
def plus_one(number):     
  return number + 1  
add_one = plus_one add_one(5)
```
- Functions can be assigned to variables, the variable then points to the same function
## Defining Functions Inside other Functions 
```python
def plus_one(number):
    def add_one(number):
        return number + 1


    result = add_one(number)
    return result
plus_one(4)
```
- Functions can also be defined inside another function
