#What is an array?
Array is a list of things used to store **Integer**, **String**, **Fixnum**, **Hash**, **Symbol** or even **another Array**. Imagin you place 7 boxs on the table, these boxes are like the memory space you get when you create an array,  for each box you put things (types listed above)in it, for example, you put a bunch of keys in the first box then it will be labled **0**, when you want to get rid of the bunch of keys you will tell ruby that, oh I want to make things inside the box **0** to be cleaned out. Now this box is empty but there is still a box there which means the memory space won't be gone after you empty a box and you can still put new things in.

##Create Arrays
#####Using `new` method to create an array.
	
	# Create an array called city, Notice capital A here
	city = Array.new
	
This is an array called `city`, though this array is not initialised nor been set size yet.
##Set array size
You can set array size by doing:
	
	city = Array.new(20)

This is an `array` contains 20 elements (20 boxes on the table this time!), each element is associated with an index pointing to it.
You can get the `size`/`length` of an `array` by doing:

	cityName = Array.new(20)

	puts cityName.size

	puts cityName.length

	# Outputs:

	20
	20

##Assignment
Assigning **repeating** things in when you created an array:

	cityName = Array.new(3,"Tokyo")

	puts "#{cityName}"

	# Outputs:

	["Tokyo", "Tokyo", "Tokyo"]

**Notice that**: when you assign some things to the `array` you also set the `size` of the `array`, in this above case the `size` is 3.

Or you can assign things using **calculation**:

	n = Array.new(10) { |x| x = x * 3}

	puts "#{n}"

	# Outputs:

	[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]


#####Using "[ ]" to create array and put assignments.
	
	# Mind the '.' sign

	n = Array.[](1, 2, 3, 4)

Alternatively:

	n = Array[1, 2, 3, 4]

The following is a method using a range as its parameter and it takes one parameter each time to create an array:

	n = Array(1..4)

	puts #{n}

	# Notice that the "a..b" means from a to b.

	# Output is:

	[1, 2, 3, 4]

### Accessing array
To access a particular element of an array, you type:

	# Create and assign values

    n = Array["Tokyo", "Yokohama", "Osaka", "Nagoya"]

    # Get the value at positin 2

    puts n[2]

    # Outputs:

    Osaka

    # Alternatively

    puts n.at(2)

    # Outputs:

    Osaka

Array is kind of an oddball in programming. You would expect the `n[2]`/ `n.at(2)` to give you the **second** element in the array which is Yokohama. __WRONG!!!__ It will return the **third** value in the array `n` which is `Osaka`. That is because `array` index it's elements starting from 0, this is not due to Ruby being special but a standard created by the first computer scientists a long time ago. Therefore:

    puts n[0]

	# Outputs:

	Tokyo

##Some examples

	manga = Array.[]("Sabaku no tami", "Imouto he", "Hikoutei jidai")
	puts "#{manga}"
	puts manga[4]
	puts manga.at(1)
	puts manga[2]

Try to figure out what will be displayed in the terminal when you run this code. :-)