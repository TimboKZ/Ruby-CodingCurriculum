# Completing challenge 1

In this part of the tutorial, you would learn how to complete a task that you have completed earlier, using new found skills so that
the code is easier to read, can be easily adapted and so it doesnt take so many lines of code.

##Putting everything together

Now ok, you have your new knowledge and you might want to apply it to something new, however if you try completing your first challenge with the new skills, you may find that it will be far easier to write and adapt.

##What you need to do

The question in the quiz are going to be exactly the same as last time, so if you are lost open up the first attempt page and look at what you are required to do for this challenge.

##Building instructions

first of all we are going to declair all the variables that we are planning to use

    $score = 0
    questionTitles = Array.new
    questionList = Array.new
    questionChoice1 = Array.new
    questionChoice2 = Array.new
    questionChoice3 = Array.new
    $correctAnswers = Hash.new

in the code above we declaired several variables. The first integer will keep the score as last time.The only global variable will be correctAnswers
which will be a hash storing correct string representations of answers. questionTitles will keep the questions.
questionList will keep a list of all possible choices for each question. Finally all the variables that start with questionChoice will have strigs of choices for the question.
----------

lets now set these variables

    questionTitles = Array["1.How do you say \"Hello\" in Japanese?", "2.What is the literal translation of Tokyo?", "3.Identify a choice that has both \"yes\" and \"no\" in Japanese?"]
    questionChoice1 = Array["Hallo", "Konichiwa", "Oyasumi", "Itadakimasu", "Ja Mate"]
    questionChoice2 = Array["Land of rising sun", "Capital", "Crazy place", "East capital", "Land of progress"]
    questionChoice3 = Array["hai, ii", "ai, pie", "yes, no", "hai, iie", "ha, ei"]
    questionList = Array[questionChoice1,questionChoice2,questionChoice3]
    $correctAnswers = Hash["Konichiwa" => 1, "East capital" => 1, "hai, iie" => 1]
    $correctAnswers.default = 0

----------
So to check if the answer is correct we are going to need a method. This method will use the advantages of hashes to determine if the user entered the correct answer

    def processAnswer
      if $correctAnswers[gets.chomp] == 1
       $score += 1
       puts "correct"
      else
    puts "INCORRECT"
      end
      puts
    end
----------
it is now time to test your looping ability

    for i in 0..(questionTitles.length-1)
      puts questionTitles[i]
      puts
      for j in 0..(questionChoice1.length-1)
        puts questionList[i][j]
      end
      puts
      processAnswer
    end
----------
now were are going to finish the code exactly like last time.

    puts "You got #{$score} in the quiz correct"
    $end


# The Final Code

----------
    $score = 0

    questionTitles = Array.new
    questionList = Array.new
    questionChoice1 = Array.new
    questionChoice2 = Array.new
    questionChoice3 = Array.new
    $correctAnswers = Hash.new
    questionTitles = Array["1.How do you say \"Hello\" in Japanese?", "2.What is the literal translation of Tokyo?", "3.Identify a choice that has both \"yes\" and \"no\" in Japanese?"]
    questionChoice1 = Array["Hallo", "Konichiwa", "Oyasumi", "Itadakimasu", "Ja Mate"]
    questionChoice2 = Array["Land of rising sun", "Capital", "Crazy place", "East capital", "Land of progress"]
    questionChoice3 = Array["hai, ii", "ai, pie", "yes, no", "hai, iie", "ha, ei"]
    questionList = Array[questionChoice1,questionChoice2,questionChoice3]
    $correctAnswers = Hash["Konichiwa" => 1, "East capital" => 1, "hai, iie" => 1]
    $correctAnswers.default = 0

    def processAnswer
      if $correctAnswers[gets.chomp] == 1
       $score += 1
       puts "correct"
      else
    puts "INCORRECT"
      end
      puts
    end

    #comment here

    for i in 0..(questionTitles.length-1)
      puts questionTitles[i]
      puts
      for j in 0..(questionChoice1.length-1)
        puts questionList[i][j]
      end
      puts
      processAnswer
    end

    puts "You got #{$score} in the quiz correct"
    $end
----------
