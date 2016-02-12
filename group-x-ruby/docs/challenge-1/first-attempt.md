# First proper program

In this part of the ruby tutorial you are going to learn on how to build a simple program, from the skills that you have gathered.
The first problem you are going to solve will be a quiz that will ask 3 questions about Japanese language and then output the player
their final score.

##Putting everything together

You might have been wondering why learn ruby? what are its applications? how is anything I learned even useful?

Now even though you covered only a minor proportion of ruby, real result can be seen already, and this is why we will practice building this program.
Over the course of this time you have learned how to use functions, variables and how to use inputs and outputs.
now you are going to put your new learned skills in practice.

##What you need to do

here is the plan of the quiz:

    Quiz details

    Challenge No.1, Quiz questions
      1.How do you say "Hello" in Japanese?
      2.What is the literal translation of Tokyo?
      3.Identify a choice that has both "yes" and "no" in Japanese?
----------

    Challenge No.1, Quiz choices
    1.
      1.Hallo
      2.Konichiwa
      3.Oyasumi
      4.Itadakimasu
      5.Ja Mate
    2.
      1.Land of rising sun
      2.Capital
      3.Crazy place
      4.East capital
      5.Land of progress
    3.
      1.hai, ii
      2.ai, pie
      3.yes, no
      4.hai, iie
      5.ha, ei

----------

    Challenge No.1, Quiz answers
      1.Konichiwa
      2.East capital
      3.hai, iie

##Building instructions

So, lets start building :) !!

    puts "1. Hallo"
    puts "2. Konichiwa"
    puts "3. Oyasumi"
    puts "4. Itadakimasu"
    puts "5. Ja Mate"
    puts

now look at the code above, you probably already know what it is supposed to do. What the code above does is outputs the first list of questions for the first
question in the quiz which is then followed by a line break.

Save this code in your editor and lets continue.
(you can run the program to see the actual output. just double click on saved file)
----------
what we want to do next is declare a couple of global variables

    $questionNumber = 1
    $score = 0

write this code prior to what you have already written, this will declare two global variables, one will keep track of the questionNumber the user is currently on
and the other will keep the score.

----------
to ease the process of building a quiz we are going to use functions
so lets write these two functions

    def nextQuestion
      print "#{$questionNumber}. "
      $questionNumber += 1
    end

the function above will increment the global variable that keeps track of the question number as well as outputting the current number.
This means that we wouldnt have to write the question number our selves and more questions can be easily added at any time.

    def processAnswer(choice, num)
      puts
      if choice==num
     $score += 1
     puts "correct"
      else
    puts "INCORRECT"
      end
      puts
    end

This second function takes two parameters, one will be the choice that the user has selected as the answer and the other will be the actual answer.

Now what this function will actually do is compare both values and if they match, the function will output "correct" and increment the users score. If the values dont match however, the output will be "INCORRECT" and the score wont be incremented.

----------

Now you have learned how to use input and output, so after outputing the first set of questions, insert this code

    choice = gets.to_i

now what this will do is set a variable named choice, which will hold the users input, to what the input actually is (converted to an integer type using .to_i)

----------

lets put everything together and make the first quiz question.

    $questionNumber = 1
    $score = 0

    def nextQuestion
      print "#{$questionNumber}. "
      $questionNumber += 1
    end

    def processAnswer(choice, num)
      puts
      if choice==num
     $score += 1
     puts "correct"
      else
    puts "INCORRECT"
      end
      puts
    end

    nextQuestion
    puts "How do you say \"Hello\" in Japanese?"
    puts

    puts "1. Hallo"
    puts "2. Konichiwa"
    puts "3. Oyasumi"
    puts "4. Itadakimasu"
    puts "5. Ja Mate"
    puts

    choice = gets.to_i

    processAnswer(choice, 2)

look at the code above, as you can see we made use of functions like processAnswer(choice, 2) and nextQuestion, this code shouldnt be difficult to understand.

you might have noticed that Hello has \" written instead of just ", now this is because ruby will think that we want to end quotation marks if we just use ", so we say \" to tell ruby that its just a character to be outputted on screen.

now try the same with the next two questions.
----------

Once you have done everything it is just the ending that is left.

    puts "You got #{$score} in the quiz correct"

    $end

enter this code so that  user will get the output of his/her score. The $end will make sure ruby terminates.

# The Final Code

----------

    $questionNumber = 1
    $score = 0

    def nextQuestion
      print "#{$questionNumber}. "
      $questionNumber += 1
    end

    def processAnswer(choice, num)
      puts
      if choice==num
     $score += 1
     puts "correct"
      else
    puts "INCORRECT"
      end
      puts
    end

    nextQuestion
    puts "How do you say \"Hello\" in Japanese?"
    puts

    puts "1. Hallo"
    puts "2. Konichiwa"
    puts "3. Oyasumi"
    puts "4. Itadakimasu"
    puts "5. Ja Mate"
    puts

    choice = gets.to_i

    processAnswer(choice, 2)
    nextQuestion
    puts "What is the literal translation of Tokyo?"
    puts

    puts "1. Land of rising sun"
    puts "2. Capital"
    puts "3. Crazy place"
    puts "4. East capital"
    puts "5. Land of progress"
    puts

    choice = gets.to_i

    processAnswer(choice, 4)
    nextQuestion
    puts "Identify a choice that has both \"yes\" and \"no\" in japanese?"
    puts

    puts "1. hai, ii"
    puts "2. ai, pie"
    puts "3. yes, no"
    puts "4. hai, iie"
    puts "5. ha, ei"
    puts

    choice = gets.to_i

    processAnswer(choice,4)
    puts "You got #{$score} in the quiz correct"

    $end


----------
