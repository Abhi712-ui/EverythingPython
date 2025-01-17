# Python Inheritance

## 1. What is Inheritance?
 - Inheritance allows a class (child) to inherit attributes and methods from another class (parent).
 - Promotes code reuse and extensibility.
```
class Parent:
    def greet(self):
        print("Hello from the parent class!")

class Child(Parent):
    pass

# The child class inherits the greet() method.
child = Child()
child.greet()
# Output: Hello from the parent class!
```


## 2. Adding Features to the Child Class
 - The child class can have additional attributes or methods beyond what is inherited.
```
class Child(Parent):
    def specific_method(self):
        print("This is a child-specific method!")

child = Child()
child.greet()  # Inherited method
child.specific_method()  # Child-specific method
# Output:
# Hello from the parent class!
# This is a child-specific method!
```

## 3. Overriding Parent Methods
 - A child class can provide its own implementation of an inherited method.
```
class Parent:
    def greet(self):
        print("Hello from the parent!")

class Child(Parent):
    def greet(self):
        print("Hello from the child!")

child = Child()
child.greet()
# Output: Hello from the child!
```

## 4. Using the `super()` Function
 - The `super()` function allows you to call a method from the parent class.
```
class Parent:
    def greet(self):
        print("Hello from the parent!")

class Child(Parent):
    def greet(self):
        super().greet()
        print("And hello from the child!")

child = Child()
child.greet()
# Output:
# Hello from the parent!
# And hello from the child!
```

## 5. Inheriting the `__init__` Method
 - Use `super().__init__()` to call the parent class's constructor.
```
class Parent:
    def __init__(self, name):
        self.name = name

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age

child = Child("Alice", 25)
print(child.name)  # Output: Alice
print(child.age)   # Output: 25
```

## 6. Multi-Level Inheritance
 - A class can inherit from another child class, forming a chain of inheritance.
```
class Grandparent:
    def greet(self):
        print("Hello from the grandparent!")

class Parent(Grandparent):
    def greet(self):
        print("Hello from the parent!")

class Child(Parent):
    pass

child = Child()
child.greet()
# Output: Hello from the parent!
```

## 7. Multiple Inheritance
 - A class can inherit from multiple parent classes.
```
class Mother:
    def speak(self):
        print("Speaking from Mother!")

class Father:
    def speak(self):
        print("Speaking from Father!")

class Child(Mother, Father):
    pass

child = Child()
child.speak()  # Calls the method from the first parent in the inheritance order
# Output: Speaking from Mother!
```

## 8. The Method Resolution Order (MRO)
 - Determines the order in which methods are searched in multiple inheritance.
```
class A:
    def method(self):
        print("Method in A")

class B(A):
    def method(self):
        print("Method in B")

class C(A):
    def method(self):
        print("Method in C")

class D(B, C):
    pass

d = D()
d.method()
# Output: Method in B

# Check the MRO using the `__mro__` attribute.
print(D.__mro__)
# Output: (<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>)
```

## 9. Checking Instance and Subclass Relationships
 - Use `isinstance()` and `issubclass()` for type checking.
```
class Parent:
    pass

class Child(Parent):
    pass

child = Child()
print(isinstance(child, Child))  # Output: True
print(isinstance(child, Parent))  # Output: True
print(issubclass(Child, Parent))  # Output: True
```

## 10. Abstract Classes in Inheritance
 - Use abstract classes to enforce method implementation in child classes.
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

# Trying to instantiate `Animal` would raise an error:
# animal = Animal()  # TypeError: Can't instantiate abstract class
```

## 11. Using Inheritance with `super()` in Methods
 - Extend functionality of a parent method in the child class.
```
class Parent:
    def greet(self):
        print("Parent greeting!")

class Child(Parent):
    def greet(self):
        super().greet()
        print("Child greeting!")

child = Child()
child.greet()
# Output:
# Parent greeting!
# Child greeting!
```
---

## 12. Combining Inheritance and Polymorphism
 - Subclasses can override parent methods to behave differently while maintaining a consistent interface.
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

animals = [Dog(), Cat(), Animal()]
for animal in animals:
    print(animal.speak())
# Output:
# Woof!
# Meow!
# I make a sound
```
