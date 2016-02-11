# Hashes

Hashes in Ruby are very similar to arrays you've learned about in the previous chapter. The main difference is quite subtle but makes a huge difference - while in arrays you use integers to access various elements, in hashes you can use an arbitrary object for the same purpose.

## Why not just use arrays?

Consider this problem: You need to make some data structure which will hold the population of various cities in Japan. Since arrays only support integer indices, you will have to assign an integer to each city:

* **0** - Kyoto
* **1** - Osaka
* **2** - Tokyo

Now we can create the array itself and access the population of different cities:

    populationInMillions = Array[1.474473, 2.666371, 8.949447]

And now we can use this array as follows:

    // Outputs the population of Kyoto
    puts populationArray[0]

    // Outputs the population of Osaka
    puts populationArray[0]

The major downside to using this method is that you have to assign each city to an integer, and whoever will be using your array in the future has to know what exactly each integer represents. Here is where hashes come into play - since you can use any object as the hash index, you can simply use strings instead of integers:

    populationInMillions = Hash["Kyoto" => 1.474473, "Osaka" => 2.666371, "" => 8.949447]

    // Outputs the population of Osaka
    puts populationInMillions["Osaka"]

## Creating hashes

The easiest way to create hashes is to create an empty hash:

    myHash = Hash.new

Now that we have created a new hash, we can add and read information from it:

    myHash["colour"] = "red"
    puts myHash["colour"]

