
# Object Oriented Programming
__Ruby__ is a pure Object Oriented Programming Language (OOP). You must remember that everything in Ruby (e.g. an integer, a decimal number or a string) is an object of a particular class.

## Classes and Objects
If programming is building a house, then a `class` would be the blueprint and the `object` would be the house or an _instance_ of a class.
### Class

A class specifies the variables(what it's object has) and methods(what it's object does). It is an abstraction of the real world object, meaning that you remove the unnecessary details of an object in order to reduce it to a set of essential characteristics.
For example, my grand parents have a Shiba Inu, a Chihuahua and a Husky, all 3 are completely different in appearance but they are all dogs, they are 4 legged animals and they can bark. Therefore I can say they are 3 objects belonging to the class __*Dog*__.
To create a class, you need type:

    class class_name

        include anything related to the class here

    end

 For example a pet dog class would have:

    class Dog

          @@number_of_legs = 4

          # Basic initializer
          def initialize(name, species, age)
            # Assign the argument to the "name" instance variable for the instance
            @name = name
            # If no age given, we will fall back to the default in the arguments list.
            @age = age

            @species = species
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

#### Instance vs Class Variables

* An **instance variable** is a variable which each instance or object of a class will have it's own copy, changes made to instance variables of one object won't affect the other objects of the same class. In Ruby, instance variables are created with **one** '@' character at the start of variable name, i.e. @name.
* A **class variable** on the other hand is a variable which is shared across all objects or instances of that class. Meaning changes made to class variables will be updated to all objects. Class variables are declared with __two__ '@' characters at the start, i.e. @@number_of_legs.

Just to make it "easier", try running and understand this small piece of code

    class Person
        @@name_class = "Kojima" # Only Class Variables can be declared out here

        def getName
            puts "Class variable: " + @@name_class
            puts "Instance variable: " + @name_instance
        end

        def initialize(name_instance)
        # Instance variables can only be declared inside class functions
            @name_instance = name_instance
        end

        def setInstance=(name)
            @name_instance = name
        end

        def setClass=(name)
            @@name_class = name
        end
    end

    person1 = Person.new("John")
    person2 = Person.new("John")

    puts "person1: "
    person1.getName
    puts "person2: "
    person2.getName

    puts "\nNow change the variables\n\n"

    person1.setInstance = ("Tanaka")
    person2.setClass = ("Sasaki")

    puts "person1: "
    person1.getName
    puts "person2: "
    person2.getName

This is the output of the program:

    person1:
    Class variable: Kojima
    Instance variable: John
    person2:
    Class variable: Kojima
    Instance variable: John

    Now change the variables

    person1:
    Class variable: Sasaki
    Instance variable: Tanaka
    person2:
    Class variable: Sasaki
    Instance variable: John




In OOP it is good practice to always have constructor, getter and setter methods in a class for ease of well... constructing an object. A _constructor_ method is used as a way to quickly create an object of the class by injecting the variable values of the class as parameter of the method. _Getter_ methods will get the values of the variable
 and _setter_ methods will set/change the value of the variables.

 Since everything is a class in Ruby, you may have noticed how you can use so called "built-in methods" with things like arrays and string.

    a_string = "Hello"
    a_string.reverse # olleH
### Objects

An object is created(instantiated) from a class. To instantiate an object, you type:

    object = class.new()

and the object `object` will have whatever is declared in the class `class`. For example if there is a function `foo()` defined in `class`, we can use it on the `object` by:

    object.foo()

 Using the class `Dog` above, we can create a dog:

    pet = Dog.new("Alex", "Husky", 10) # Create a pet Dog

    # Getter
    # puts is used to display on the screen
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