# Smartphone class representing different brands: Samsung, iPhone, and Oppo
class Smartphone:
    def __init__(self, brand, model, storage, price):
        self.brand = brand
        self.model = model
        self.storage = storage
        self.price = price

    def display_info(self):
        print(f"Brand: {self.brand}")
        print(f"Model: {self.model}")
        print(f"Storage: {self.storage} GB")
        print(f"Price: ${self.price}")
    
    def call(self, number):
        print(f"Calling {number}...")
    
    def take_picture(self):
        print(f"Taking a picture with {self.model}'s camera...")

# Subclass of Smartphone (Inherit and add more details)
class Samsung(Smartphone):
    def __init__(self, model, storage, price, has_s_pen):
        super().__init__("Samsung", model, storage, price)
        self.has_s_pen = has_s_pen

    def display_info(self):
        super().display_info()
        print(f"S Pen: {'Included' if self.has_s_pen else 'Not Included'}")

class iPhone(Smartphone):
    def __init__(self, model, storage, price, face_id):
        super().__init__("iPhone", model, storage, price)
        self.face_id = face_id

    def display_info(self):
        super().display_info()
        print(f"Face ID: {'Enabled' if self.face_id else 'Not Enabled'}")

#  instances of different smartphones
samsung_phone = Samsung("Galaxy S23", 128, 999, True)
iphone_phone = iPhone("iPhone 14", 128, 1099, True)

# Display smartphone information
samsung_phone.display_info()
iphone_phone.display_info()

# Call and take picture actions
samsung_phone.call("123-456-7890")
iphone_phone.take_picture()













# Polymorphism with Vehicle Classes

# Base class: Vehicle
class Vehicle:
    def move(self):
        pass  # Empty base method to be overridden by subclasses

class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

class Bicycle(Vehicle):
    def move(self):
        print("Pedaling 🚴")

# instances of each vehicle
vehicles = [Car(), Plane(), Bicycle()]

# Loop through each vehicle and call the move method
for vehicle in vehicles:
    vehicle.move()  # Polymorphism in action: each move() method is defined differently

