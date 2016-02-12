#What is a loop?
Loops can be used when you want to repeatedly do things.
For example, I would like to have 5 lines of **"Ruby is awesome!"**, instead of typing 5 times we can use a loop to help us achieve this. The most basic loop of all is a _while_ loop Let's create a file and name it, here we do __**While.rb**__

##__**while**__
	
	while conditional (do)
	
		code 
	
	end
	
	--------or-------

	begin

		code

	end while conditional

Let's look at a specific example:

	counter = 0

	while counter < 5

		puts "Ruby is awesome!"

		counter++

	end

Also you can write:

	counter = 0

	begin

		puts "Ruby is awesome!"

		counter++

	end while counter < 5

Run the program, on the terminal you will see:

	Ruby is awesome!
	Ruby is awesome!
	Ruby is awesome!
	Ruby is awesome!
	Ruby is awesome!

In this case

 *	**counter < 5** is the condition

 *	**puts "Ruby is awesome!"** is the loop body.

The loop body will continuously repeating if the condition is **true**, stop until the condition is **false**. 

At the beginning **counter = 0**, 0 is less than 5 so the condition is true then we will get into the loop body to process the __**puts**__ method, after we finish we do **counter++**, which means counter plus 1, so now **counter = 1**, it is still true, we go back to the start of the loop, do the puts method second time, keep doing this until counter = 5, when the condition is false, okay we jump out of the while loop and goes to **"end"**, the program is complete when it reaches **"end"**.

## There are many loops
`While` loop is the most basic of all loops but it is rather "inconvenient" to use for everything. Therefore, Ruby comes equipped with a variety of ways to declare loops that will help making your code more straight forward.

##__**until**__

The __**until**__ loop is a alternative way which does exactly the same thing as __**while**__ does. An __**until**__ loop will repeat until the condition is **true**, i.e stops when the condition is **true**.

	until conditional (do)

		code

	end

	--------or--------

	begin

		code
	
	end until conditional

A more specific example of __**until**__ method:

	counter = 0

		until counter > 5

		puts counter

		counter++

	end

Same as before you can put __**until**__ at the end:

	counter = 0

	begin

		puts counter

		counter++

	end until counter > 5

The output on the terminal is:

	0
	1
	2
	3
	4
	5
---

##__**for**__##

The __**for**__ loop is another way of doing loops, it has the structure of:

	for variable (,variable...) in expression (do)

		code

	end

Let's see an example:

	for x in 0..3

		puts "X is #{x}"

	end

On the terminal:

	X is 0
	X is 1
	X is 2
	X is 3
---

__**Each**__

In ruby, there is another method does exactly the same thing as __**for..in**__ does, it's structure is like this:

	(expression).each (do) |variable(,variable...)| 

		code

	end

Let's do the same example:

	(0..5).each do |x|

		puts "X is #{x}"

	end

On the terminal:

	X is 0
	X is 1
	X is 2
	X is 3

##__**break**__
Break will stop the loops.

for example:
	
	for x in 0..3
	
		if x > 2 then
	
			break
	
		end
	
		puts "X is #{x}"
	
	end

On the terminal:

	X is 0
	X is 1
	X is 2
