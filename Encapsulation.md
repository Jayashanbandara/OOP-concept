# OOP-concept

➡️ Encapsulation

Encapsulation is the bundling of data (attributes) and methods (functions) that operate on the data into a single unit called a class. It helps in hiding the internal details of an object and exposing only what is necessary.

class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def start_engine(self):
        print(f"The {self.make} {self.model}'s engine is started.")
        
my_car = Car("Toyota", "Camry")
my_car.start_engine()


