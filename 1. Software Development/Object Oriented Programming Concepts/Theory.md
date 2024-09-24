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

<br>

---

<br>

Sure! Below, you'll find detailed explanations of key Object-Oriented Programming (OOP) concepts: Abstraction, Association, Encapsulation, Composition, Polymorphism, Aggregation, Inheritance, and Message Passing. Each explanation includes examples in C++, Java, and Python, along with diagrams to help visualize these concepts.

## 1. Abstraction

### Definition:
Abstraction is the concept of hiding the complex implementation details and exposing only the necessary features of an object. This simplifies interaction with objects and makes code easier to maintain and understand.

### Key Points:
- Focus on essential characteristics.
- Use abstract classes and interfaces to achieve abstraction.

### Examples:
- **C++:**
  ```cpp
  class Shape {
  public:
      virtual void draw() = 0; // Pure virtual function
  };

  class Circle : public Shape {
  public:
      void draw() override {
          cout << "Drawing Circle" << endl;
      }
  };
  ```

- **Java:**
  ```java
  abstract class Shape {
      abstract void draw();
  }

  class Circle extends Shape {
      void draw() {
          System.out.println("Drawing Circle");
      }
  }
  ```

- **Python:**
  ```python
  from abc import ABC, abstractmethod

  class Shape(ABC):
      @abstractmethod
      def draw(self):
          pass

  class Circle(Shape):
      def draw(self):
          print("Drawing Circle")
  ```

### Diagram:
```
 +----------------+
 |    Shape       |
 |----------------|
 | + draw()       |
 +----------------+
          |
          |
 +----------------+
 |    Circle      |
 |----------------|
 | + draw()       |
 +----------------+
```

---

## 2. Association

### Definition:
Association represents a relationship between two objects where both can exist independently. It describes how one object interacts with another.

### Key Points:
- Types of association: one-to-one, one-to-many, many-to-one, many-to-many.
- Does not imply ownership.

### Examples:
- **C++:**
  ```cpp
  class Driver {
      // Driver properties
  };

  class Car {
      Driver* driver; // Association with Driver
  };
  ```

- **Java:**
  ```java
  class Driver {
      // Driver properties
  }

  class Car {
      Driver driver; // Association with Driver
  }
  ```

- **Python:**
  ```python
  class Driver:
      pass

  class Car:
      def __init__(self, driver):
          self.driver = driver  # Association with Driver
  ```

### Diagram:
```
+---------+      +---------+
|  Driver |      |   Car   |
+---------+      +---------+
```

---

## 3. Encapsulation

### Definition:
Encapsulation is the bundling of data (attributes) and methods (functions) that operate on the data into a single unit or class. It restricts direct access to some of an object's components, which is a means of preventing accidental interference.

### Key Points:
- Use access modifiers (private, protected, public).
- Enhances security and reduces complexity.

### Examples:
- **C++:**
  ```cpp
  class Account {
  private:
      double balance; // Private data

  public:
      void deposit(double amount) {
          balance += amount; // Public method
      }
  };
  ```

- **Java:**
  ```java
  class Account {
      private double balance; // Private data

      public void deposit(double amount) {
          balance += amount; // Public method
      }
  }
  ```

- **Python:**
  ```python
  class Account:
      def __init__(self):
          self.__balance = 0  # Private attribute

      def deposit(self, amount):
          self.__balance += amount  # Public method
  ```

### Diagram:
```
+--------------------+
|      Account       |
|--------------------|
| - balance          |  (private)
|--------------------|
| + deposit(amount)  |  (public)
+--------------------+
```

---

## 4. Composition

### Definition:
Composition is a strong form of association where one class contains references to one or more objects of another class. The lifetime of the contained objects is tied to the lifetime of the container object.

### Key Points:
- Strong ownership relationship.
- Contained objects cannot exist without the container.

### Examples:
- **C++:**
  ```cpp
  class Engine {
      // Engine properties
  };

  class Car {
  private:
      Engine engine; // Composition
  };
  ```

- **Java:**
  ```java
  class Engine {
      // Engine properties
  }

  class Car {
      private Engine engine; // Composition
  }
  ```

- **Python:**
  ```python
  class Engine:
      pass

  class Car:
      def __init__(self):
          self.engine = Engine()  # Composition
  ```

### Diagram:
```
+-------+
|  Car  |<--- contains
+-------+
| - engine |
+-------+
```

---

## 5. Polymorphism

### Definition:
Polymorphism allows objects to be treated as instances of their parent class. It enables a single interface to represent different underlying data types.

### Key Points:
- Achieved through method overriding and overloading.
- Enhances flexibility and maintainability.

### Examples:
- **C++:**
  ```cpp
  class Shape {
  public:
      virtual void draw() { cout << "Drawing Shape" << endl; }
  };

  class Circle : public Shape {
  public:
      void draw() override { cout << "Drawing Circle" << endl; }
  };
  ```

- **Java:**
  ```java
  class Shape {
      void draw() {
          System.out.println("Drawing Shape");
      }
  }

  class Circle extends Shape {
      void draw() {
          System.out.println("Drawing Circle");
      }
  }
  ```

- **Python:**
  ```python
  class Shape:
      def draw(self):
          print("Drawing Shape")

  class Circle(Shape):
      def draw(self):
          print("Drawing Circle")
  ```

### Diagram:
```
          +-------------+
          |    Shape    |
          |-------------|
          | + draw()    |
          +-------------+
                 |
                 |
          +-------------+
          |   Circle    |
          |-------------|
          | + draw()    |
          +-------------+
```

---

## 6. Aggregation

### Definition:
Aggregation is a special form of association that represents a "whole-part" relationship where the part can exist independently of the whole. It shows that one class can contain references to objects of another class.

### Key Points:
- Weaker relationship than composition.
- Parts can exist independently.

### Examples:
- **C++:**
  ```cpp
  class Department {
      // Department properties
  };

  class Company {
      Department* department; // Aggregation
  };
  ```

- **Java:**
  ```java
  class Department {
      // Department properties
  }

  class Company {
      Department department; // Aggregation
  }
  ```

- **Python:**
  ```python
  class Department:
      pass

  class Company:
      def __init__(self, department):
          self.department = department  # Aggregation
  ```

### Diagram:
```
+-----------+      +-----------+
| Department|      |  Company  |
+-----------+      +-----------+
```

---

## 7. Inheritance

### Definition:
Inheritance is the mechanism by which one class (child or subclass) can inherit properties and behaviors (methods) from another class (parent or superclass). It promotes code reuse and establishes a relationship between classes.

### Key Points:
- Types: single, multiple, multi-level, hierarchical, and hybrid inheritance.
- Supports method overriding.

### Examples:
- **C++:**
  ```cpp
  class Animal {
  public:
      void speak() { cout << "Animal speaks" << endl; }
  };

  class Dog : public Animal {
  public:
      void speak() { cout << "Dog barks" << endl; }
  };
  ```

- **Java:**
  ```java
  class Animal {
      void speak() {
          System.out.println("Animal speaks");
      }
  }

  class Dog extends Animal {
      void speak() {
          System.out.println("Dog barks");
      }
  }
  ```

- **Python:**
  ```python
  class Animal:
      def speak(self):
          print("Animal speaks")

  class Dog(Animal):
      def speak(self):
          print("Dog barks")
  ```

### Diagram:
```
         +-----------+
         |  Animal   |
         +-----------+
         | + speak()  |
         +-----------+
                |
                |
         +-----------+
         |    Dog    |
         +-----------+
         | + speak()  |
         +-----------+
```

---

## 8. Message Passing

### Definition:
Message passing is the process by which objects communicate with each other by sending and receiving messages (method calls). It is a fundamental way for objects to interact in OOP.

### Key Points:
- Encapsulates object communication.
- Encourages loose coupling between objects.

### Examples:
- **C++:**
  ```cpp
  class Car {
  public:
      void start() {
          cout << "Car started" << endl;
      }
  };

  class Driver {
      void drive(Car& car) {
          car.start(); // Message passing
      }
  };
  ```

- **Java:**
  ```java
  class Car {
      void start() {
          System.out.println("Car started");
      }
  }



  class Driver {
      void drive(Car car) {
          car.start(); // Message passing
      }
  }
  ```

- **Python:**
  ```python
  class Car:
      def start(self):
          print("Car started")

  class Driver:
      def drive(self, car):
          car.start()  # Message passing
  ```

### Diagram:
```
+----------+         +---------+
|   Car    |         | Driver  |
+----------+         +---------+
| + start()|         | + drive()|
+----------+         +---------+
        |-------------------|
                 Message
```

---

### Conclusion

These OOP concepts form the foundation of modern programming and are essential for exam preparation, especially for SBI SCO roles. Make sure to understand each concept thoroughly, as they often appear in various forms during technical interviews and assessments.

#### Tips for Exam Preparation:
- Understand the differences between related concepts (e.g., composition vs. aggregation).
- Practice coding examples to reinforce your understanding.
- Review the diagrams and examples regularly to aid memory retention.

If you need further details or specific questions related to SBI SCO, feel free to ask!
