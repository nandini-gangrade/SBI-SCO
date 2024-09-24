# OOPs
Object-Oriented Programming (OOP) is a paradigm centered on the concept of "objects", which can be data structures, functions, or both. In the context of software development, OOP concepts like **Abstraction, Encapsulation, Polymorphism, Inheritance**, and others help in organizing and structuring code for better maintainability and reuse.

## 1. **Abstraction**
   **Definition**: 
   Abstraction refers to hiding the complex implementation details and showing only the essential features of an object. It helps to reduce the complexity of code by exposing only the relevant data or behavior to the user.
   
   **Example**: 
   Consider a `Car` class. The user doesn’t need to know the internal working of the engine. They just need to know that they can `start()` and `stop()` the car.
   ```python
   class Car:
       def start(self):
           print("Car started.")
   
       def stop(self):
           print("Car stopped.")
   
   # User only interacts with 'start' and 'stop', without knowing the internal engine workings.
   car = Car()
   car.start()
   car.stop()
   ```
   
   **MCQ**:
   1. Which of the following best describes Abstraction in OOP?
      - a) Providing unnecessary details about the implementation
      - b) Hiding implementation details and showing only essential functionality
      - c) Using multiple classes in a single object
      - d) Creating complex systems
   
      **Answer**: b) Hiding implementation details and showing only essential functionality

## 2. **Association**
   **Definition**: 
   Association defines the relationship between two separate classes, where one class uses or interacts with another. The relationship can be one-to-one, one-to-many, many-to-one, or many-to-many.
   
   **Example**: 
   A `Teacher` can have multiple `Students`, but a student can have multiple teachers as well. This is an example of a many-to-many association.
   
   ```python
   class Teacher:
       def __init__(self, name):
           self.name = name
   
   class Student:
       def __init__(self, name):
           self.name = name
   
   t1 = Teacher("Mr. Smith")
   s1 = Student("John")
   # Association between Teacher and Student.
   ```
   
   **MCQ**:
   1. Association between two classes means:
      - a) One class is a type of another class
      - b) One class is composed of another class
      - c) One class knows about another class and can interact with it
      - d) All the objects share common data
   
      **Answer**: c) One class knows about another class and can interact with it

## 3. **Encapsulation**
   **Definition**: 
   Encapsulation is the bundling of data (attributes) and methods (functions) into a single unit or class. It also restricts access to certain properties, typically using access specifiers like `private`, `protected`, and `public`.
   
   **Example**: 
   ```python
   class Person:
       def __init__(self, name, age):
           self.__name = name  # Private attribute
           self.__age = age    # Private attribute
   
       def get_name(self):
           return self.__name
   
       def set_name(self, name):
           self.__name = name
   ```
   Here, the attributes `__name` and `__age` are encapsulated within the class and can only be accessed through methods like `get_name()` and `set_name()`.
   
   **MCQ**:
   1. Encapsulation is:
      - a) Hiding implementation details from the user
      - b) Storing multiple methods in one class
      - c) Combining data and functions into a single unit and restricting access
      - d) Only defining functions inside a class
   
      **Answer**: c) Combining data and functions into a single unit and restricting access

## 4. **Composition**
   **Definition**: 
   Composition is a type of association where one class is made up of one or more instances of other classes. It represents a **"has-a"** relationship.
   
   **Example**: 
   A `Car` has an `Engine`. If the car is destroyed, so is the engine, representing a strong association.
   ```python
   class Engine:
       def __init__(self, horsepower):
           self.horsepower = horsepower
   
   class Car:
       def __init__(self, model, engine):
           self.model = model
           self.engine = engine  # Composition
   
   engine = Engine(300)
   car = Car("Toyota", engine)
   ```
   
   **MCQ**:
   1. In a composition relationship, when the container object is destroyed:
      - a) The contained object also gets destroyed
      - b) The contained object remains unaffected
      - c) The relationship between objects is one-to-many
      - d) None of the above
   
      **Answer**: a) The contained object also gets destroyed

## 5. **Polymorphism**
   **Definition**: 
   Polymorphism means "many forms". It allows objects of different classes to be treated as objects of a common superclass, particularly when they share methods. It comes in two forms: **Method Overloading** and **Method Overriding**.
   
   **Example (Method Overloading)**:
   ```python
   class Math:
       def add(self, a, b):
           return a + b
   
       def add(self, a, b, c):
           return a + b + c
   ```
   
   **Example (Method Overriding)**:
   ```python
   class Animal:
       def sound(self):
           pass
   
   class Dog(Animal):
       def sound(self):
           return "Bark"
   
   class Cat(Animal):
       def sound(self):
           return "Meow"
   
   animal = Dog()
   print(animal.sound())  # Output: Bark
   ```
   
   **MCQ**:
   1. What is Polymorphism?
      - a) A class with many subclasses
      - b) A method that can perform multiple functions
      - c) Objects of different classes that share a method and behave differently
      - d) Classes that inherit from one another
   
      **Answer**: c) Objects of different classes that share a method and behave differently

## 6. **Aggregation**
   **Definition**: 
   Aggregation is a weak form of association where one class is made up of multiple instances of other classes. Unlike composition, in aggregation, the contained object can exist independently.
   
   **Example**:
   A `Department` has multiple `Employees`. Even if the department is removed, the employees still exist.
   
   ```python
   class Employee:
       def __init__(self, name):
           self.name = name
   
   class Department:
       def __init__(self, employees):
           self.employees = employees  # Aggregation
   
   emp1 = Employee("John")
   emp2 = Employee("Doe")
   dept = Department([emp1, emp2])
   ```
   
   **MCQ**:
   1. Which of the following best describes Aggregation?
      - a) A "has-a" relationship where both objects can exist independently
      - b) A "has-a" relationship where both objects depend on each other for existence
      - c) A "part-of" relationship
      - d) None of the above
   
      **Answer**: a) A "has-a" relationship where both objects can exist independently

## 7. **Inheritance**
   **Definition**: 
   Inheritance allows a class (child/subclass) to inherit properties and methods from another class (parent/superclass). It provides a way to reuse code and build hierarchies.
   
   **Example**:
   ```python
   class Animal:
       def __init__(self, name):
           self.name = name
   
   class Dog(Animal):
       def bark(self):
           print(f"{self.name} says Woof!")
   
   dog = Dog("Buddy")
   dog.bark()  # Output: Buddy says Woof!
   ```
   
   **MCQ**:
   1. Inheritance allows:
      - a) A class to inherit properties and methods from a superclass
      - b) An object to modify its properties
      - c) Two classes to have the same properties
      - d) None of the above
   
      **Answer**: a) A class to inherit properties and methods from a superclass

## 8. **Message Passing**
   **Definition**: 
   Message passing refers to the process where objects communicate with each other by sending messages, usually by calling methods on objects.
   
   **Example**:
   ```python
   class Calculator:
       def add(self, a, b):
           return a + b
   
   calc = Calculator()
   result = calc.add(5, 3)  # Message passing (method call)
   print(result)  # Output: 8
   ```
   
   **MCQ**:
   1. In OOP, message passing refers to:
      - a) Storing messages in a queue
      - b) Calling methods on an object
      - c) Communicating between two classes
      - d) Passing objects between functions
   
      **Answer**: b) Calling methods on an object
```
