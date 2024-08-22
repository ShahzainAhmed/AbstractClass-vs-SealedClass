# Difference Between Abstract and Sealed Classes

## Abstract Class
- ### Purpose:
  An abstract class is like a blueprint. It can't be used directly but is meant to be extended by other classes. It may contain methods that don't have an implementation, which forces the subclasses to provide their own implementation.

- ### Real-World Example:
  Imagine a general blueprint for a vehicle. You can't drive a "Vehicle" because it's just an idea. But you can have a "Car" or a "Bike" that are specific types of vehicles. The "Vehicle" blueprint (abstract class) might have something like "startEngine()", but how exactly you start the engine would be different for a car or a bike, so those details are left for the specific subclasses to define.

 - ### Code Example:
    ```
    abstract class Vehicle {
      void startEngine(); // Abstract method
    }
    
    class Car extends Vehicle {
      @override
      void startEngine() {
        print('Car engine started');
      }
    }
    
    class Bike extends Vehicle {
      @override
      void startEngine() {
        print('Bike engine started');
      }
    }
    ```

## Sealed Class:
- ### Purpose:
  A sealed class is like a list of specific options you can choose from, but no one can add new options outside of the ones you provided. This ensures that all possible subclasses are defined in one place, making it easier to manage and predict behavior.

- ### Real-World Example:
  Think of a sealed class like a menu at a restaurant with a fixed number of dishes. The restaurant decides what dishes are available (subclasses), and you can't add new dishes to the menu. You know exactly what options are available, and no surprises can come from outside.

 - ### Code Example:
    ```
    sealed class Vehicle {}
    
    class Car extends Vehicle {}
    class Bike extends Vehicle {}
    ```
    Here, Vehicle is sealed, meaning only Car and Bike can be its types, and no other class outside this file can become a Vehicle.

## Summary:
- ### Abstract Class:
  It's a general template that other classes can build upon, and anyone can extend it in any file.
- ### Sealed Class:
  It tightly controls the subclasses, ensuring that only specific, predefined options exist, and no new options can be added outside of the original file.
