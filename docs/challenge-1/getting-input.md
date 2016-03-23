# Getting user input and producing output

There are many different ways to get input and produce output in Ruby, but in this part of our tutorial we will only look at several examples. To complete Challenge #1 we don't need to know them all, so we will try to focus on the parts that we require to solve the problem at hand.

## Output: `print` and `puts` methods

The first thing we will talk about will be printing text to console. Remember the `puts` method that was introduced in the previous chapter? Now you will find out what it really does.

Essentially, both `puts` and `print` accomplish the same task:

    # Using puts :

    puts "Hello World!"
    
    # OR using print:
    
    print "Hello World!"

Both produce the same output:

    Hello World!

But there is one subtle difference - `puts` method always insert a new line after the output. Consider this example:

    # print example:
    
    print "First"
    print "second"

    # puts example:
    
    puts "First"
    puts "Second"

If you execute above examples separately you will see the difference - `print` produces this output:

    # print output:
    
    FirstSecond

While `puts` prints every word on a new line:

    # puts output:
    
    First
    Second

A quick note: You can make `print` function exactly like `puts` by adding a so called "new line character" to the end of your string, which looks like this: `\n`. For example:

    print "First\n"
    print "Second"

    # Output:

    First
    Second

### When should I use each of them?

It really depends on the situation and after you get some experience you will be able to tell easily whether you should use `print` and `puts`. For now, as a general rule of thumb, I would say if you are sure that you need to print a message on a new line, go for `puts`. Otherwise, if you are, say, trying to compose a sentence out of several words, then use `print`. (Check out example below to understand what I mean)

    print "Hello "
    print "Yoko, "
    print "how "
    print "are you today?"

    # Produces:
    
    Hello Yoko, how are you today?

## Getting input

### Strings

The most common way to get user input in Ruby is the `gets` method. The usage is quite trivial:

    print "Enter your name: "
    name = gets
    puts "Hello #{name}!"

If you execute the code above you will notice that it doesn't quite output what we want it to output - in fact, it moves the exclamation mark to a new line:

    # Output of the code above:
    Enter your name: Haruhi
    Hello Haruhi
    !

You can take a guess what happens and see if you were correct in the next paragraph.

The exclamation mark gets moved to a new line because the `gets` function also reads a new line character after the input:

    some_input = gets

    # You type in "Haruhi" and press enter

    # The value of "some_input" is now:
    
    "Haruhi\n"

Luckily, Ruby gives us a way to remove that unwanted `\n`, which is also known as the new line character, using the method called `chomp`:

    print "Enter your name: "
    name = gets.chomp
    puts "Hello #{name}!"

    # Now if you input "Haruhi" the output is

    Hello Haruhi!

Now we get exactly what we want... Or do we? In some cases you might actually want to preserve the new line character in the end, so it is completly up to you to decide whether to use the `chomp` function or not.

### Numbers

The process of getting numbers as input is very similar to the process of getting strings, with one subtle difference - you have to use an additional method on the return value of the `gets` method. To start with we will only be getting integers:

    my_integer = gets.chomp.to_i
    # You type, say, 10, and the new value of
    # my_integer is 10 in its number representation

## Something for you to try

//TODO