#What is an array?
Array is a list of things used to store **Integer, String, Fixnum, Hash, Symbol or even another Array**.

##Create Arrays
#####Using "__**new**__" method.

---
	
	name = Array.new

---

Okay, now you created an Array called **name**, it is not initialized nor been set size. 

##Set array size
You can set array size by doing:

---

	name = Array.new(20)

---

This is a array contains 20 elements, each element is associated with an index pointing to it.
You can get the size/length of an array by doing:

---

	names = Array.new(20)

	puts names.size

	puts names.length

---

The output is:

---
	20
	20
---

##Assignment
Assigning **repeating** things in when you created an array:

---

	names = Array.new(3,"home")

	puts "#{names}"

---

Here **3** is the number of times you want the string after to repeat.

The output is:

---
	["home", "home", "home"]
---

Or you can assign things using calculation:

---

	n = Array.new(10) { |x| x = x * 3}

	puts "#{n}"

---

The output is:

---
	[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
---


#####Using "[ ]" to create array and put assignments.

---

	n = Array.[](1, 2, 3, 4)

---

Alternatively:

---

	n = Array[1, 2, 3, 4]

---

The following is a method using a range as its parameter and it takes one parameter each time to create an array:

---

	n = Array(1..4)

	puts #{n}

---

Notice that the **"a..b"** means **from a to b**.

The output is:

---
	[1, 2, 3, 4]
---

### Accessing array
To access a particular element of an array, you type:

    n = Array[1, 2, 3, 4]
    n[2]
    # alternatively
    n.at(2)

Array is kind of an oddball in programming. You would expect the last 2 lines of code to give you the second element in the array which is 2. __WRONG!!!__ It will return the third value in the array `n` which is 3.
Array index it's elements starting from 0, this is not due to Ruby being special but a standard created by the first computer scientists a long time ago. Therefore,

    n[0]

will give you 1.