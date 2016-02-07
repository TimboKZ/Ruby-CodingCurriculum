# Built-in functions

#The Core API

In order to make thing easier for us, Ruby comes equipped with a vast amount of built-in functions (or methods). As you may have noticed when you were learning about Arrays(hyperlink leads to Array page here), there are things you can do such as append another element to the end of the array or get an element out of the array. For example:

    an_array = [1,2,3,4,5]
    puts an_array

this will produce

    1
    2
    3
    4
    5

Now add this line after it

    an_array.push(6)
    puts an_array # display the new array

We get

    1
    2
    3
    4
    5
    6

You can also reverse with <span style="color:red">an_array.reverse</span> and many more.  
These are built in methods of the __Core API__ (let's understand it as a library), which doesn't require you to import anything extra to use it, every class has it's own built in functions such as String, Hash, etc...

##The Standard Library

Sometimes you will encounter situations where there's no function in the Core library for you to use, that is when you have to resort to using the __Standard Library__. In order to use it, you need to include at the start of your Ruby program the line

    require "standard_library_name"

"standard_library_name" can be any library that you require to complete the task.
For example: 
You are asked to calculate the square root of a complex number, there are 2 ways to go about doing it:
>1. You go and create a method that will take in a number (i.e. -1) or a complex number and return the square root of it. __Highly NOT recommended.__
>2. You use CMath library like so:

    require "cmath"

    puts CMath.sqrt(-1) # => 0+1.0i

----------

"How do I know whether I should use the Core or Standard Library?" You might ask. The answer is rather unexciting, you need to read the [Ruby Documentation](http://ruby-doc.org). Thankfully, libraries and functions are named in a straight forward manner such as date and time related functions are all in a library called DateTime.  
This is actually how programmers work, most of their time is spent reading the documentation of the language they are using to look for that required function.