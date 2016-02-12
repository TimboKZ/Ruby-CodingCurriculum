
# Object Oriented Programming
__Ruby__ is a pure Object Oriented Programming Language (OOP), that means that everything in Ruby (i.e. an integer) is an object of a particular class.

## Classes and Objects
If programming is building a house, then a `class` would be the blueprint and the `object` would be the house or an _instance_ of a class.
### Class

A class specifies the variables(what it's object has) and methods(what it's object does), for example a pet dog class would have:

    class Dog

          @@number_of_legs = 4

          # Basic initializer
          def initialize(name, species, age)
            # Assign the argument to the "name" instance variable for the instance
            @name = name
            # If no age given, we will fall back to the default in the arguments list.
            @age = age

            @species = species;
          end

          # Basic setter method
          def name=(name)
            @name = name
          end

          # Basic getter method
          def name
            @name
          end

          def species
            @species
          end

          def age
            @age
          end

          def legs
          	@@number_of_legs
          end

          def bark
            puts "bark,bark,bark"
          end
    end

As you can see, any variable with two '@' before it `@@number_of_legs` is a class variable. It is shared by all instances(objects) of this class. A dog should always have 4 legs, a name, age, species and the ability to bark which we will display "bark" 3 times.
In OOP it is good practice to always have constructor, getter and setter methods in a class for ease of well... constructing an object. A _constructor_ method is used as a way to quickly create an object of the class by injecting the variable values of the class as parameter of the method. _Getter_ methods will get the values of the variable
 and _setter_ methods will set/change the value of the variables.
### Objects

An object is created(instantiated) from a class. Using the class `Dog` above, we can create a dog:

    pet = Dog.new("Alex", "Husky", 10) # Create a pet Dog

    # Getter

    puts pet.name # Alex
    puts pet.species # Husky
    puts pet.age # 10
    pet.bark # bark, bark, bark
    puts pet.legs # 4

    # Setter

    pet.name = ("John")
    puts pet.name # John

With this, we can create as many pet dogs as we want without having to write the methods of class `Dog` over and over again. This is one of the many reasons why OOP is so powerful and preferred by many.

    not_cat = Dog.new("Milo", "German Shepherd", 5)
    a_dog = Dog.new("Mayhem", "Chihuahua", 2)

    not_cat.name # Milo
    a_dog.species # Chihuahua

### But wait, there's more
Not only being able to reduce the tedious process of writing the code again, OOP can provide security with __encapsulation__, robustness with __polymorphism__ and even more less writing the same code with __inheritance__.
