## Polymorphism

#### Class Polymorphism
* *Polymorphism** uses methods from another class to perform different tasks
* Polymorphism performs a single action in different ways. It is evident in data overriding in: **operators** , 
**methods** and **classes**
* Polymorphism means* "many forms"

```
class Cat:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def info(self):
        print(f"I am a cat. My name is {self.name}. I am {self.age} years old.")

    def make_sound(self):
        print("Meow")


class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def info(self):
        print(f"I am a dog. My name is {self.name}. I am {self.age} years old.")

    def make_sound(self):
        print("Bark")


cat1 = Cat("Kitty", 2.5)
dog1 = Dog("Fluffy", 4)

for animal in (cat1, dog1):
    animal.make_sound()
    animal.info()
    animal.make_sound()
```
In the code above, ```cat``` and ```dog``` have the same method names ```info ``` and   ```make sound``` with different 
outputs 
due to polymorphism 

#### Method Overriding - Inheritance and Polymorpism 
``` bash
from math import pi


class Shape:
    def __init__(self, name):
        self.name = name

    def area(self):
        pass

    def fact(self):
        return "I am a two-dimensional shape."

    def __str__(self):
        return self.name


class Square(Shape):
    def __init__(self, length):
        super().__init__("Square")
        self.length = length

    def area(self):
        return self.length**2

    def fact(self):
        return "Squares have each angle equal to 90 degrees."


class Circle(Shape):
    def __init__(self, radius):
        super().__init__("Circle")
        self.radius = radius

    def area(self):
        return pi*self.radius**2


a = Square(4)
b = Circle(7)
print(b)
print(b.fact())
print(a.fact())
print(b.area())
```
```str``` has been overriden in the child classes, and were used from the parent class

The ```fact()``` method for ```a(Square)``` is overridden. Whereas object ```b``` isn't overriden, it used the Parent 
```shape``` class'