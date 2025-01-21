# Python Polymorphism

## 1. What is Polymorphism?
 - Polymorphism means "many forms."
 - It allows methods in different classes to have the same name but behave differently based on the object calling them.

## 2. Polymorphism with Inheritance
 - A child class can override a method in the parent class, and the same method name can behave differently.
```
class Animal:
    def speak(self):
        return "I make a sound"

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

# Polymorphism in action
animals = [Dog(), Cat(), Animal()]
for animal in animals:
    print(animal.speak())
# Output:
# Woof!
# Meow!
# I make a sound
```
---

## 3. Polymorphism with Functions
 - Functions can take objects of different classes and call the same method on them.
```
class Bird:
    def fly(self):
        return "I can fly!"

class Penguin:
    def fly(self):
        return "I cannot fly, but I swim!"

def describe_fly(thing):
    print(thing.fly())

describe_fly(Bird())    # Output: I can fly!
describe_fly(Penguin()) # Output: I cannot fly, but I swim!
```

## 4. Polymorphism with Abstract Classes
 - Use abstract classes to enforce polymorphic behavior.
```
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

    def perimeter(self):
        return 2 * 3.14 * self.radius

# Polymorphic behavior
shapes = [Rectangle(4, 5), Circle(3)]
for shape in shapes:
    print("Area:", shape.area())
    print("Perimeter:", shape.perimeter())
# Output:
# Area: 20
# Perimeter: 18
# Area: 28.26
# Perimeter: 18.84
```

## 5. Polymorphism with Duck Typing
 - Python supports dynamic typing, meaning polymorphism works if objects implement the required method, regardless of class.
```
class Sparrow:
    def fly(self):
        return "Sparrow is flying!"

class Airplane:
    def fly(self):
        return "Airplane is flying!"

def fly_things(thing):
    print(thing.fly())

fly_things(Sparrow())  # Output: Sparrow is flying!
fly_things(Airplane()) # Output: Airplane is flying!
```

## 6. Polymorphism with Built-In Functions
 - Many Python functions exhibit polymorphic behavior.
```
# Example with len():
print(len("Hello"))    # Output: 5 (length of a string)
print(len([1, 2, 3]))  # Output: 3 (length of a list)
print(len({"a": 1, "b": 2}))  # Output: 2 (length of a dictionary)

# Example with + operator (overloaded)
print(5 + 3)           # Output: 8 (integer addition)
print("Hello" + " World")  # Output: Hello World (string concatenation)
```

## 7. Polymorphism in Operator Overloading
 - You can redefine how operators work for your custom classes using magic methods like `__add__`.
```
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)

    def __repr__(self):
        return f"Vector({self.x}, {self.y})"

v1 = Vector(1, 2)
v2 = Vector(3, 4)
v3 = v1 + v2
print(v3)
# Output: Vector(4, 6)
```

## 8. Method Overloading (Simulated)
 - Python does not support method overloading directly, but you can simulate it using default arguments.
```
class Calculator:
    def multiply(self, a, b=1):
        return a * b

calc = Calculator()
print(calc.multiply(5))       # Output: 5 (uses default value for b)
print(calc.multiply(5, 3))    # Output: 15
```

## 9. Method Overriding in Polymorphism
 - Override a method to provide specific behavior for a subclass.
```
class Vehicle:
    def start(self):
        return "Starting the vehicle"

class Car(Vehicle):
    def start(self):
        return "Starting the car"

class Bike(Vehicle):
    def start(self):
        return "Starting the bike"

vehicles = [Car(), Bike()]
for vehicle in vehicles:
    print(vehicle.start())
# Output:
# Starting the car
# Starting the bike
```

## 10. Key Takeaways About Polymorphism
- Polymorphism allows code to be flexible and reusable.
- It ensures that objects of different types can use the same interface.
- Python supports polymorphism naturally through duck typing, inheritance, and dynamic typing.
