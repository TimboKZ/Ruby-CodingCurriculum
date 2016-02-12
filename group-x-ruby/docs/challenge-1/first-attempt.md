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
----------



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
