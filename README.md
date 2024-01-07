➡️ Encapsulation -Acces level control

Encapsulation is the bundling of data (attributes) and methods (functions) that operate on the data into a single unit called a class. It helps in hiding the internal details of an object and exposing only what is necessary.

    class Car:
      def __init__(self, make, model):
          self.make = make
          self.model = model

      def start_engine(self):
          print(f"The {self.make} {self.model}'s engine is started.")

    # Usage
    my_car = Car("Toyota", "Camry")
    my_car.start_engine()

➡️ Inheritance - Can access a class things with a another class(Called inherit)

❕four inheritance
    1.single inheritance
    2.Hierarchical inheritance
    3.Multi Level Inheritance
    4.Multiple Inheritance
    5.Hybrid Inheritance


Inheritance allows a new class (subclass/derived class) to inherit properties and methods from an existing class (superclass/base class). It promotes code reusability and establishes a relationship between the classes.

     class Animal:
        def speak(self):
            pass

    class Dog(Animal):
        def speak(self):
            return "Woof!"

    class Cat(Animal):
        def speak(self):
            return "Meow!"

    # Usage
    dog = Dog()
    cat = Cat()

    print(dog.speak())  # Output: Woof!
    print(cat.speak())  # Output: Meow!



➡️ Polymorphism - One thing has different situation has different acts

Can achieve 
   1.Method Overloading
   2.Method Overiding

Polymorphism allows objects of different classes to be treated as objects of a common base class. It enables a single interface for different data types.

    class Shape:
        def area(self):
            pass

    class Circle(Shape):
        def __init__(self, radius):
            self.radius = radius

        def area(self):
            return 3.14 * self.radius * self.radius

    class Rectangle(Shape):
        def __init__(self, length, width):
            self.length = length
            self.width = width

        def area(self):
            return self.length * self.width

    # Usage
    circle = Circle(5)
    rectangle = Rectangle(4, 6)

    print(circle.area())      # Output: 78.5
    print(rectangle.area())   # Output: 24


➡️ abstraction - reduce the complexity


Abstraction is another important concept in object-oriented programming (OOP). It involves simplifying complex systems by modeling classes 
based on the essential properties and behaviors that they share, while hiding the unnecessary details. Abstraction allows you to focus on 
what an object does rather than how it achieves its functionality.


    class Shape(ABC):
        @abstractmethod
        def area(self):
            pass
    
    # Concrete class implementing the abstract class
    class Circle(Shape):
        def __init__(self, radius):
            self.radius = radius
    
        def area(self):
            return 3.14 * self.radius * self.radius
    
    # Concrete class implementing the abstract class
    class Rectangle(Shape):
        def __init__(self, length, width):
            self.length = length
            self.width = width
    
        def area(self):
            return self.length * self.width
    
    # Usage
    circle = Circle(5)
    rectangle = Rectangle(4, 6)
    
    print(circle.area())      # Output: 78.5
    print(rectangle.area())   # Output: 24

➡️ Composition

  Composition is the concept of creating complex objects by combining simpler objects or components. Instead of relying solely on inheritance, you can compose objects by including instances of other classes as attributes. This promotes code reuse and flexibility.

    class Engine:
        def start(self):
            print("Engine started")
    
    class Car:
        def __init__(self):
            self.engine = Engine()
    
        def start(self):
            print("Car started")
            self.engine.start()
    
    # Usage
    my_car = Car()
    my_car.start()

➡️ Interfaces

An interface is a collection of abstract methods that define a contract for classes that implement it. Unlike abstract classes,
interfaces in some languages (like Java) cannot contain any implementation. They specify what methods a class must provide, ensuring a consistent interface for multiple classes.

    from abc import ABC, abstractmethod
    
    class Shape(ABC):
        @abstractmethod
        def area(self):
            pass
    
    class Circle(Shape):
        def __init__(self, radius):
            self.radius = radius
    
        def area(self):
            return 3.14 * self.radius * self.radius
    
    class Rectangle(Shape):
        def __init__(self, length, width):
            self.length = length
            self.width = width
    
        def area(self):
            return self.length * self.width



➡️ Dependency Injection

Dependency Injection is a design pattern that emphasizes the passing of dependencies (e.g., objects, services) into a class rather than having the class create or manage them. 
This promotes loose coupling, making the code more modular and testable.

    class Engine:
        def start(self):
            print("Engine started")
    
    class Car:
        def __init__(self, engine):
            self.engine = engine
    
        def start(self):
            print("Car started")
            self.engine.start()
    
    # Usage
    my_engine = Engine()
    my_car = Car(my_engine)
    my_car.start()

    
➡️ Polymorphic Associations

    class Dog:
        def sound(self):
            return "Woof!"
    
    class Cat:
        def sound(self):
            return "Meow!"
    
    class PetOwner:
        def __init__(self, pet):
            self.pet = pet
    
        def get_pet_sound(self):
            return self.pet.sound()
    
    # Usage
    dog_owner = PetOwner(Dog())
    cat_owner = PetOwner(Cat())
    
    print(dog_owner.get_pet_sound())  # Output: Woof!
    print(cat_owner.get_pet_sound())  # Output: Meow!

➡️ Single Responsibility Principle (SRP)

SRP states that a class should have only one reason to change, meaning that a class should have only one responsibility or job. 
This promotes maintainability and reduces the likelihood of introducing bugs when making changes.
    

➡️ Open/Closed Principle (OCP):

OCP states that a class should be open for extension but closed for modification. This encourages the use of interfaces and 
abstract classes to allow for easy extension without altering existing code
