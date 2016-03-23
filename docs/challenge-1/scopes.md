# Ranges in Ruby

Ranges are very important to all programming languages and luckily Ruby does support scope, so why don't we take a tour on **range** now?

There are 3 main usage of scopes:

* Ranges as Sequences
* Ranges as Conditions
* Ranges as Intervals

##Ranges as sequences
As the first and the most common used one, range is used to display sequences. A sequence got one start point, one end point and a way to create continuous values.
In Ruby we use ".." and "..." to create these ranges. ".." means include the edges while "..." means ignore the edges. Let's look at some examples:

	(1..6)     

	# ==>1, 2, 3, 4, 5, 6

	(1...6)       

	# ==>1, 2, 3, 4. 5

	('a'..'d')    
	
	# ==>'a', 'b', 'c', 'd'

###`to_a` method
Converting a range to a list:

	$, = ", "
	# Array value sepatator

	num = (1..5).to_a
	elem = ('car'..'cat').to_a

	puts "#{num}"
	puts "#{elem}"

	# Outpus:

	1, 2, 3, 4, 5
	car, cas, cat

###Some implementation methods: `include?`, `min`, `max`, `reject`, `each do`:

	# Assume a range

	num = 0..7

	puts num.include?(5)

	ret = num.min

	puts "Min value is #{ret}"

	ret = num.max

	puts "Max value is #{ret}"

	ret = nun.reject {|i| i < 5 }

	puts "Rejected values are #{ret}"

	num.each do |num|

		puts "In Loop #{num}"

	end


Outputs:


	true
	Min value is 0
	Max value is 7
	Rejected values are 5, 6, 7
	In Loop 0
	In Loop 1
	In Loop 2
	In Loop 3
	In Loop 4
	In Loop 5
	In Loop 6
	In Loop 7

##Ranges as conditions
Ranges can also be used as conditional expressions in this format:

	while gets

		print if /start/../end/

	end
"start" and "end" above hold the conditions, if the input `gets` value is within then range from "start" to "end" (including), it will go though `print`. Here is an example, in `case` statements:

	grade = 88

	result = case grade

		when 0..40 then "Fail"
		when 41..60 then "Pass"
		when 61..70 then "Pass with Merit"
   		when 71..100 then "Pass with Distinction"
    	else "Invalid Score"

	end

	puts result

Outputs:

	Pass with Distinction

##Ranges as intervals
The case equality operator, `===`, used to see if some value fall within the interval represented by the range.

	if ((1..7) === 5)
		puts "5 lies in (1..7)"
	end

	if (('a'..'j') === 'c')
  		puts "c lies in ('a'..'j')"
	end

	if (('a'..'j') === 'z')
	  	puts "z lies in ('a'..'j')"
	end

Outputs:

	5 lies in (1..10)
	c lies in ('a'..'j')

