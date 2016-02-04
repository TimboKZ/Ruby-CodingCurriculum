# First proper program

----------
##Putting everything together

Over the course of this time you have learned how to use functions... now you are going to put your learned skills in practice
##What you need to do

blah blah blah

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
