#Input and Output#
There are some basic function in the I/O that you can use directly to get user inputs or give outputs. For example __**read, write, gets, puts, readline, getc**__ and __**printf**__.

##__**puts**__##
Create a file called __**samplePuts.rb**__  (or any name you like). Remember that all the ruby files will end up with __**.rb**__. Edit it with:

---

	val1 = "First variable"

	val2 = "Second variable"

	puts val1

	puts val2

---

There are two ways to run your program:
>1. Using __**ruby puts.rb**__
      *  Open the terminal
      *  Change it into the directory where you saved your program(use **cd** command, type **ls** then **ENTER** to see all files contained in this directory) 
      *  Run the program by typing **ruby puts.rb** (The space must be shown), press ENTER.
2. Using __**load 'samplePuts.rb'**__
      *  Type **irb** to get into the IRB prompt
      *  Then type **load 'samplePuts.rb'**, press ENTER.

On the terminal you will get the following:

---

	First variable

	Second variable

---

In this example you give a string to the variable name v1 and v2, then use __**puts**__ method to tell the computer that I want these variables to be printed out, thus we know __**puts**__ print the whole string. Also notice that after it finish the first __**puts**__, it automatically _return to a new line_ and do the second __**puts**__, thus __**puts**__ print things with a new line.

##__**gets**__##
Create another file and name it as __**sampleGets.rb**__, add the followings in and save it.

---

	puts "Enter a value: "

	val = gets

	puts "The value you entered is: "
	
	puts val

---

Once you run it in the terminal, you will get:

---

	Enter a value:

	6 						

	The value you entered is: 

	6						

---

Basicall __**gets**__ function ask you to type things in the terminal and pass the whole thing you typed to the variable that holds the value.

##__**putc**__##
Create a file called __**samplePutc.rb**__.

---

	str = "Hello Ruby!"

	putc str

----

You will get:

---

	H

---

Oh what's going on here, why is there only one 'H', we are expecting "Hello Ruby!" to be printed out in the terminal. Yes, that's what **putc** does, print out only **one character** not a string.

##__**print**__##

---

	print "Hello World"

	print "Hello Ruby"

---

Save and run, you get:

---
	
	Hello WorldHello ruby

---

Ahha, it doesn't return to a new line after it finish the **print** function, so everything will be layout on the same line unlike the **puts** function.


######There is a question, what if you have **a hundred of line that needs to be entered**? Maybe you would prefer to store all the inputs in a text file. Yes we are going to learn how to read a file. First you need to learn how to create, open and close a file using __**File.new, File.open, File.close**__######

##__**File.new**__ and __**File.open**__##
Using __**mode**__ to determine what you want to do with the created file. 
Here are some **modes** you can choose:

>1. r:  Read only. Starts from the beginning.
2.	r+: Read and write. Starts from the beginning.
3.	w:  Write only. If there exist a file already, rewrite everything, otherwise create 	 a new one to write in.
4. w+: Read and write. If there exist a file already, rewrite everything, otherwise 		create a new one to write in.
5. a:  Write only. The same as **w** except that this is adding things to the original 	 file.
6. a+: Read and Write. Adding things to the original file.

You can use __**File.new**__ to create a file:

----

	aFile = File.new("txtFilename", "mode")

	aFile.close

----

* filename: choose whatever you like
* mode: choose from above to fit your desire e.g. r, r+, w and so on.

You can use __**File.open**__ to open a file:

---

	File.open("filename", "mode") do |aFile|

	end

---

Notice the **"do |aFile|"** part, only __**File.open**__ can be followed by method but __**File.new**__ cannot.


##__**sysread**__##
This is a method to read file, while using __**sysread**__ method you are free to choose any mode to open the file. Okay Let's try it.
>1. Same as before create a file, let's name it as __**Read.rb**__.
2. Put "This is a test file to be read" in a new text file saved as **input.txt**.

In the Read.rb:

---
	aFile = File.new("input.txt", "r")

	if aFile

		content = aFile.sysread(20)

		puts content

	else

		puts "Uable to open file"

	end

---

This will print out the first **20** characters, and the pointer will point at the 21st position of the characters.


##__**syswrite**__##
You will use this method to write content into a text file, so that you must using r+ mode to open the file, here comes an example:

---

	aFile = File.new("input.txt", "r+")

	if aFile

	aFile.syswrite("Hello")

	else

	puts "Uable to open file"

	end

---

This will add "Hello" into the text file.

##__**IO.readlines**__##
This method read the file line by line and store each line into an array.

---

	array = IO.readlines("input.txt")

	puts array[0]

	puts array[1]

---

Array[0] will contain the first line of the file, and array[1] contains the second line and so on.