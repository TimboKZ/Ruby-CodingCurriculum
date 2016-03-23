#What is a loop?

Imagine you are told to display `Ruby is awesome!` 5 times by some weird Ruby nuts, up until now the obvious way to do this would be to type:

    puts "Ruby is awesome!"
    puts "Ruby is awesome!"
    puts "Ruby is awesome!"
    puts "Ruby is awesome!"
    puts "Ruby is awesome!"

Now, imagine you are asked to do it 100 times, again to save some time you would use copy and paste 99 times but this way of doing a task repeatedly have many disadvantages. Firstly if you actually did it 100 times, your hands will probably hate you and the source code file will be filled with

    puts "Ruby is awesome!"

Which looks __REALLY UGLY__ and takes up storage. Moreover, imagine you have to display

    Ruby is awesome 1
    Ruby is awesome 2
    Ruby is awesome 3
    Ruby is awesome 4
    Ruby is awesome 5
    ...

up until **"Ruby is awesome 100"**, using copy and paste is not viable anymore since you have to change the number at the end of each line of code anyway. So how do we solve this? Enter __Loops__.

As the name suggests, using loops is a way to do a task such as displaying "Ruby is awesome" repeatedly. Additionally, you can do the task as many times as you want as long as the loop is active. The most basic loop of all is a __**while**__ loop Let's create a file and name it, here we do __**Loop.rb**__

Here is how a __**while**__ loop is structured
##__**while**__
	
	while conditional (do)
	
		code 
	
	end
	
	# --------or-------

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

	# Outputs

	Ruby is awesome!
	Ruby is awesome!
	Ruby is awesome!
	Ruby is awesome!
	Ruby is awesome!

In this case

 *	`counter < 5` is the condition

 *	`puts "Ruby is awesome!"` is the loop body.

The loop body will continuously repeating if the condition is **true**, stop until the condition is **false**. 

At the beginning `counter = 0`, 0 is less than 5 so the condition is true then we will get into the loop body to process the `puts` method, after we finish we do `counter++`, which means increase the value of `counter` variable by 1, so now `counter = 1`, it is still **true**, we go back to the start of the loop, do the puts method second time, keep doing this until counter = 5, when the condition is false, okay we jump out of the while loop and goes to `end`, the program is complete when it reaches the `end`.

__Now try displaying "Ruby is awesome!" a hundred times.__

## There are many loops
`While` loop is the most basic of all loops but it is rather "inconvenient" to use for everything. Therefore, Ruby comes equipped with a variety of ways to declare loops that will help making your code more straight forward.

##__**until**__

The `until` loop is a alternative way which does exactly the same thing as `while` does. An `until` loop will repeat until the condition is **true**, i.e stops when the condition is **true**.

	until conditional (do)

		code

	end

	# --------or--------

	begin

		code
	
	end until conditional

A more specific example of `until` method:

	counter = 0

		until counter > 5

		puts counter

		counter++

	end

Same as before you can put ｀until｀ at the end:

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

The ｀for｀ loop is another way of doing loops, it has the structure of:

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

##__**Each**__

In ruby, there is another method does exactly the same thing as `for..in` does, it's structure is like this:

	(expression).each (do) |variable(,variable...)| 

		code

	endw

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
`break` will stop the loops.

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


## Something for you to try
Display

    Ruby is awesome 1
    Ruby is awesome 2
    Ruby is awesome 3
    Ruby is awesome 4
    Ruby is awesome 5

up until "Ruby is awesome 20" using every single flavour of loops that has been introduced in this chapter.