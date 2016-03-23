# Inheritance

Inheritance in Ruby is just the relation between 2 classes where the child class inherits the methods and variables defined in the parent class. Consider this example: You have a class named `Vehicle` and it has a method called `drive()`. Now, you want to have some way to refer to motorcycles and vans, but although both are vehicles there are some important differences - for example, unlike motorcycles, vans should have a `lockDoors()` method.

### Understanding inheritance

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

# Encapsulation

Encapsulation is all about protecting the internal structure of an object from any outside changes. That is to say that whoever is going to use our objects can only access the public methods, while the internal structure and private methods are hidden. By abstracting any data manipulation to specific methods, we make sure that the whole program doesn't depend on a specific line of code but a method as a whole, and as long as this method returns the expected value the program will work regardless of how this value was calculated.

Here's a simple example of encapsulation:

    class Coat
      attr_accessor :size
     
      def initialize(size)
        @size = size
      end
     
      def set_name(size)
        @size = size
      end
    end
    
    coat = Coat.new(10)
     
    # Change the coat size
    coat.set_name(11)
     
Notice how I could easily change the `size` variable stored in the coat object using public methods and without actually accessing the variable itself.

# Polymorphism

Polymorphism is the idea of abstracting different elements behind the same interface. Unfortunately polymorphism is quite hard to implement in Ruby so a concept known as **duck typing** is used instead.

### Duck typing

Consider this example: You have 2 shapes, `circle` and `square`, each with a separate class and a `draw` method. You want to be able to draw whatever shape you get, regardless of whether it is a `circle` or a `square`. This is how you can approach this problem using duck typing:

    # First, let's define the class for each shape
    class Circle
      def draw
        # Draw method specific to circles
      end
    end
    
    class Square
      def draw
        # Draw method specific to squares
      end
    end
    
    # Now let's make a generic class that will draw any shape
    class Shape
      def draw(shape)
        shape.draw
      end
    end
    
    circle_or_square = Circle.new # You can change this to Square.new and the program will still work
    
    shape = Shape.new
    shape.draw(circle_or_square)
    
As you can see, the `draw` method in the `Shape` class simply expects anything with `draw` method defined, so regardless of the type of object you use, it will call the `draw` method for the particular object mimicking polymorphism behaviour.