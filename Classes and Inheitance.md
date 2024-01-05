```python
class Employee:
	"""Doc String goes here"""
	company = "CompName" # class variable common to all instances
    def __init__(self, name, age):
        self.name =  name   # instance variable unique to instance
        self.age = age
	def __str__(self):
		return f"{self.name} is {self.age} years old"
```
- `__init__` instantiates new instances of a class
- `--str__`  gives an informal string representation of the class, it's what gets printed out when you try print an object of the class
# Inheritance
```python
class Parent:
    hair_color = "brown"

class Child(Parent):
    pass
```
- child classes inherit attributes from their parent classes and can override or extend those attributes
- 