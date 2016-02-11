# Inheritance

Inheritance in Ruby is just the relation between 2 classes where the child class inherits the methods and variables defined in the parent class. Consider this example: You have a class named `Vehicle` and it has a method called `drive()`. Now, you want to have some way to refer to motorcycles and vans, but although both are vehicles there are some important differences - for example, unlike motorcycles, vans should have a `lockDoors()` method.

## Understanding inheritance

Let's try to translate the example above from English into Ruby. First of all, we have to define the `Vehicle` class:

    class Vehicle
      def drive
        # Drive somewhere
      end
    end

Now, we need to create separate class for vans that will ihnerit from the `Vehicle` class. Note that the symbol `<` is used to denote inheritance:

    class Van < Vehicle
      def lock_doors
        # Lock doors
      end
    end

Since `Van` inherits from `Vehicle`, it has all of the methods that `Vehicle` class has, namely the `drive` method. This also means that if we change the way `drive` method works in the `Vehicle` class, changes will affect all child classes immmediately, saving us the trouble of changing each class manually.

You can access the methods inherited from the parent class just like you access any other methods:

    van = Van.new
    van.drive
    van.lock_doors
