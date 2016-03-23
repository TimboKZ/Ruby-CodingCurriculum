# Variables in Ruby

In Ruby you store all of your information, such as numbers and strings, in variables. There are several types of variables used in Ruby and this part of challenge #1 will introduce you to all of them.

## Number variables

### A quick example

Below you can find a simple example of usage of variables, don't try to think about too much yet - we'll explain how exactly it works later.

    first_variable = "Some Value"
    integer_variable = 1
    
The code above simply means that the variable with the name `first_variable` now holds a value of `Some Value`, which is a string. `integer_variable` on the other holds value of `1`, which, as the name implies, is an integer. As you can see any variable in Ruby can hold any value, regardless of its type - whether it is a decimal number, integer, string or even a collection of strings (don't worry about them for now, we'll talk about them in other tutorials).

> _The process of assigning a value to a variable is referred to as **initialising**. For example, assigning a value of `10` to a variable named `box_size` can be called initialising variable `box_size` to `10`._

I want to quickly introduce a simple function called `puts`. You will learn more about it in the next chapter about output, but for now all you need to know is that this function prints the value of the variable supplied to it. Consider this example:

    # Define some variable
    my_variable = 1234
    
    # This function will output the value of my_variable
    puts my_variable
    # Outputs "1234"
    
We will use the `puts` function to see the values currently stored in our variables.

### Naming conventions

In the example above you might've noticed that each variable must have a name. In Ruby, there are specific coding conventions regarding the way you name strings, but do not worry, they are quite straight forward:

* First of all, the variable names are **case-sensitive**. This means that `VaRiAbLe` and `variable` are considered to be 2 different variables.
* Secondly, variable names must only contain alphanumeric characters or underscores (`_`). That is to say you can only use letters A to Z, digits 0 to 9 and the `_` symbol when naming a variable.
* A variable name cannot begin from a capital letter.

For now, following these points will suffice. At a later stage we will introduce you to a couple more concepts in variable naming and different variable types.

> **Note**: To make your variable names more descriptive try composing them from several words separated by underscores, i.e.:

    # Price of a single car in pounds
    car_price_in_GBP = 400
    
### What are variables useful for?

> *To simplify the learning process for now let's only consider variables that store numbers for now.*

You can do various manipulations with variables. For now, let's focus on the basic operations such as addition, subtraction, division and multiplication.

    integer = 10
    decimal_number = 2.5
    sum_variable = integer + decimal_number
    difference = integer - decimal_number
    product_variable = integer * decimal_number
    
As you can see, the variables above hold the result of the operation corresponding to their names. For example, `difference` now contains the value of `7.5`. An important feature of variables is that if you change one variable, all other variables that depend on it will change too: In this case, if we were to initialise `integer` to `8` instead of `10`, the values of `sum_variable`, `difference` and `product_variable` would change too.

When initialising a variable to a number you can use parentheses just like you would do in algebra. Try to run the code below to confirm that the answer is correct:

    decimal_number = (10 * 6.17) / 4.9 - 5
    
    puts decimal_number
    
There are many reasons why variables are extremely useful. Consider this simple example:

> You are an owner of a shop that only sells 1 type of product and you're currently having a sale. For each customer, you know the amount of the product they want to buy,w the price and the discount. The thing you want to calculate is the amount of money the customer will have to pay for their order.

Here is how we you can implement it:

    # Price of a single product
    price = 20
    
    # Discount in %
    discount = 10
    
    # Quantity to be bought
    quantity = 20
    
    # Now we begin our calculation
    price_after_discount = price * (100 - discount) / 100
    
    amount_to_pay = price_after_discount * quantity
    
    # And finally we print the answer
    puts amount_to_pay
    
Now that the code is ready, you can just change the value of `price`, `discount` or `quantity` to any other values and your program will calculate the rest for you. As you will find out in later tutorials, there are much better ways to do it but this solution will do for now.

## Strings

Strings can be the values of variables just like numbers:

    my_string = "This is my string!"
    hello = "Hello World!"

They have many interesting features, but for now let's focus on the important parts.

First of all, you can combine strings (and other types of variables):

    hello = "Hello"
    name = "Yoko"
    hello_string = hello + " " + name + "!"

    # Now the value of 'hello_string' is the following string:
    Hello Yoko!

Additionally, you must know that you don't have to use the `+` to combine strings, there is a much neater way:

    name = "Yoko"
    hello_string = "Hello #{name}!"

    # 'hello_string' now holds the same value as in previous example:
    Hello Yoko!

Same method also works with other types of variables (and even expressions):

    x = 10
    y = 5
    first_string = "The value of x is #{x}"
    second_string = "The sum of x and y is #{x + y}"

    # Value of 'first_string':
    The value of x is 10

    # Value of 'second_string':
    The sum of x and y is 15

## Some examples for you to try

First of all, let's see if you understand how operations with numbers work in Ruby. Try to predict the output of this simple program:

    number_1 = 10
    number_2 = 24
    number_3 = number_2 * 2 - number_1 * 3
    
    result = (number_3 + number_1) / 7
    
    puts result
    
Now try to execute this code is see if you were correct.