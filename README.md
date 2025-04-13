# OOP-ASSIGNMENT
ACTIVITY 1
# Base class: Superhero
class Superhero:
    def __init__(self, name, alias, power, level=1):
        # Public attributes
        self.name = name               # Real name of the superhero
        self.alias = alias             # Superhero nickname
        self.power = power             # Main superpower
        # Private attribute to demonstrate encapsulation
        self.__level = level           # Level indicates strength or experience

    # Getter method for the private attribute __level
    def get_level(self):
        return self.__level

    # Setter method for the private attribute __level
    def set_level(self, level):
        if level > 0:
            self.__level = level
        else:
            print("Level must be a positive integer!")

    # Method to display superhero's information
    def display_info(self):
        print(f"Superhero: {self.name} aka {self.alias}")
        print(f"Power: {self.power} | Level: {self.__level}")

    # Method for training to increase the superhero's level
    def train(self):
        self.__level += 1
        print(f"{self.name} has trained and is now level {self.__level}!")

# Derived class: FlyingSuperhero
class FlyingSuperhero(Superhero):
    def __init__(self, name, alias, power, level=1, flying_speed=100):
        # Call the base class constructor to initialize common attributes
        super().__init__(name, alias, power, level)
        self.flying_speed = flying_speed  # Additional attribute exclusive to flying heroes

    # Overridden method to also display flying speed (demonstrating polymorphism)
    def display_info(self):
        # Call the base version to print common info
        super().display_info()
        print(f"Flying Speed: {self.flying_speed} km/h")

    # New method specific to FlyingSuperhero
    def fly(self):
        print(f"{self.name} soars through the sky at {self.flying_speed} km/h!")

# Example usage of the classes
if __name__ == '__main__':
    # Create an instance of Superhero
    hero1 = Superhero("Clark Kent", "Superman", "Super strength", level=5)
    hero1.display_info()
    hero1.train()  # Demonstrates modification of the private attribute through a method

    print("\n-----\n")
    
    # Create an instance of FlyingSuperhero
    hero2 = FlyingSuperhero("Diana Prince", "Wonder Woman", "Agility & Wisdom", level=4, flying_speed=200)
    hero2.display_info()  # Shows polymorphism by the overridden method
    hero2.fly()           # Calls the method unique to FlyingSuperhero

    ACTIVITY 2
    # Define a Car class with a custom move() method.
class Car:
    def move(self):
        print("Driving 🚗")


# Define a Plane class with its own version of the move() method.
class Plane:
    def move(self):
        print("Flying ✈️")


# Define a Boat class with a different move() method.
class Boat:
    def move(self):
        print("Sailing 🚤")


def main():
    # Create instances of each class.
    car = Car()
    plane = Plane()
    boat = Boat()

    # Polymorphism in action: iterate over a sequence of vehicles
    # and call the same method 'move()' on each.
    vehicles = [car, plane, boat]
    for vehicle in vehicles:
        vehicle.move()


if __name__ == '__main__':
    main()

