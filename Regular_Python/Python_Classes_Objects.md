# Python Classes and Objects

## 1. Creating a Class
 - Use the `class` keyword to define a class.
```
class Person:
    pass  # Placeholder for now

person1 = Person()
print(person1)
# Output: <__main__.Person object at 0x...>
```
## 2. The `__init__` Method (Constructor)
 - Used to initialize object attributes.
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person1 = Person("Alice", 25)
print(person1.name)  # Output: Alice
print(person1.age)   # Output: 25
```
## 3. Object Methods
 - Define methods inside the class that act on the object.
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

person1 = Person("Bob", 30)
print(person1.greet())
# Output: Hello, my name is Bob and I am 30 years old.
```
## 4. Modifying Object Properties
 - Change the attributes of an object directly.
```
person1.age = 31
print(person1.age)
# Output: 31
```
## 5. Adding Methods Dynamically
 - Add methods to an object outside of the class definition.
```
def say_goodbye(self):
    return f"Goodbye from {self.name}!"

Person.say_goodbye = say_goodbye
print(person1.say_goodbye())
# Output: Goodbye from Bob!
```
## 6. Class Variables
 - Variables shared by all instances of the class.
```
class Person:
    species = "Human"  # Class variable

    def __init__(self, name):
        self.name = name  # Instance variable

person1 = Person("Alice")
person2 = Person("Charlie")
print(person1.species)  # Output: Human
print(person2.species)  # Output: Human
Person.species = "Homo sapiens"
print(person1.species)  # Output: Homo sapiens
```
## 7. Instance Variables vs. Class Variables
 - Instance variables are unique to each object, while class variables are shared.
```
class Example:
    shared = []  # Class variable

    def __init__(self):
        self.unique = []  # Instance variable

e1 = Example()
e2 = Example()
e1.shared.append("Shared value")
e1.unique.append("Unique to e1")
print(e1.shared)  # Output: ['Shared value']
print(e2.shared)  # Output: ['Shared value']
print(e1.unique)  # Output: ['Unique to e1']
print(e2.unique)  # Output: []
```
## 8. Inheritance
 - A class can inherit attributes and methods from another class.
```
class Animal:
    def speak(self):
        return "I make a sound"

class Dog(Animal):
    def speak(self):
        return "Woof!"

dog = Dog()
print(dog.speak())
# Output: Woof!
```
## 9. The `super()` Function
 - Call methods from the parent class.
```
class Animal:
    def __init__(self, species):
        self.species = species

class Dog(Animal):
    def __init__(self, species, breed):
        super().__init__(species)
        self.breed = breed

dog = Dog("Canine", "Labrador")
print(dog.species)  # Output: Canine
print(dog.breed)    # Output: Labrador
```
## 10. Encapsulation
 - Use underscores to indicate private attributes.
```
class Person:
    def __init__(self, name):
        self._name = name  # Protected attribute
        self.__age = 25    # Private attribute

    def get_age(self):
        return self.__age

person1 = Person("Alice")
print(person1._name)  # Output: Alice
print(person1.get_age())  # Output: 25

# Accessing a private attribute directly raises an error:
# print(person1.__age)  # AttributeError
```
## 11. Polymorphism
 - Different classes can implement the same method.
```
class Cat(Animal):
    def speak(self):
        return "Meow!"

animals = [Dog(), Cat()]
for animal in animals:
    print(animal.speak())
# Output:
# Woof!
# Meow!
```
## 12. Static Methods
 - Define a method that doesn’t depend on class or instance variables.
```
class Math:
    @staticmethod
    def add(a, b):
        return a + b

print(Math.add(3, 5))
# Output: 8
```
## 13. Class Methods
 - Define a method that works with the class itself, not instances.
```
class Person:
    count = 0

    def __init__(self, name):
        self.name = name
        Person.count += 1

    @classmethod
    def total_persons(cls):
        return cls.count

person1 = Person("Alice")
person2 = Person("Bob")
print(Person.total_persons())  # Output: 2
```
## 14. `__str__` and `__repr__` Methods
 - Customize the string representation of an object.
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"{self.name}, {self.age} years old"

    def __repr__(self):
        return f"Person(name={self.name}, age={self.age})"

person = Person("Alice", 25)
print(person)  # Output: Alice, 25 years old
print(repr(person))  # Output: Person(name=Alice, age=25)
```
## 15. Abstract Classes
 - Define a blueprint for classes using the `abc` module.
```
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

dog = Dog()
print(dog.speak())
# Output: Woof!
```
