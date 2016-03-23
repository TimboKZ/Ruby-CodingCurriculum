# Completing Challenge 2
If you have managed to create a Tic Tac Toe game, __GREAT JOB!!!__ If you haven't been able to make it, worry not because this section will be about explaining my approach and my code for this game, you can use this as reference or go straight to Challenge 3 for more awesome Ruby.

---

## Get classy
My __Player__ class has a name, score and a set of moves. In __choose_move__ function, my logic is as follows:

* Parameter is the list of taken moves in order to compare with the move chosen by the user.
* Display the name of player, prompt the player to enter the move.
* If the move is taken or invalid, display the error message based on the circumstances. Repeat these 2 steps until a valid move that is not taken is chosen.
* Add the move to the `moves` list.
* Return the move chosen by the user.


        class Player
              attr_accessor :name, :moves, :score

          def initialize(name)
            @name = name
            @moves
            @score = 0
          end

          def choose_move(taken_moves)
            puts "Your character is #{name}. Choose an available position on the board:"
            next_move = gets.chomp.to_i # Take the string input and convert to integer

            while move_taken?(next_move, taken_moves) || !valid_move?(next_move)
              if move_taken?(next_move, taken_moves)  # If move is taken
                puts "That move is already taken! Try again:"
                next_move = gets.chomp.to_i
              end
              if (valid_move?(next_move) == false)  # If move is not a valid one
                puts "#{next_move} is not a valid position, please choose a position on the board:"
                next_move = gets.chomp.to_i
              end
            end

            @moves.push(next_move) # Add the move to the set of moves, push makes @moves become an array
            return next_move
          end
        end


__Board__ class contain 2 arrays:

* `board` to contain the characters to be placed in by the player.
* `taken_moves` to contain the moves that have been taken by the players.

It has 3 methods:

* __display__ takes care of displaying the board
* __update__ which takes in the `number` which represents the position on the board and `letter` which represents the letter to be put in that position (again, either X or O).

        class Board
              attr_accessor :board, :taken_moves

          def initialize
            @board = ['', '', '', '', '', '', '', '', ''] # positions on the board
            @taken_moves = [] # the positions that have been chosen
          end

          def display
            puts "Here is the current game board:"
            puts "\t#{@board[0]}\t|\t#{@board[1]}\t|\t#{@board[2]}"
            puts "--------------------------"
            puts "\t#{@board[3]}\t|\t#{@board[4]}\t|\t#{@board[5]}"
            puts "--------------------------"
            puts "\t#{@board[6]}\t|\t#{@board[7]}\t|\t#{@board[8]}"
          end

          def update(number, letter)
            @taken_moves.push(number) # add the  position number to the list of taken moves
            board[number - 1] = letter # put the character of the player (X or O) into the position to be displayed on the board
          end
        end

## The functions
The helper functions are mostly check whether the move is valid and if the game has ended and the result of the game. These functions are pretty self explanatory and I commented in the code so you are able to understand the meaning of each line.

---

## The Final Code
This is it, the final working code. Save it as a .rb file, run it and play against your friends(and win)!
See you in Challenge 3.

    class Player
      attr_accessor :name, :moves, :score

      def initialize(name)
        @name = name
        @moves
        @score = 0
      end

      def choose_move(taken_moves)
        puts "Your character is #{name}. Choose an available position on the board:"
        next_move = gets.chomp.to_i # Take the string input and convert to integer

        while move_taken?(next_move, taken_moves) || !valid_move?(next_move)
          if move_taken?(next_move, taken_moves)  # If move is taken
            puts "That move is already taken! Try again:"
            next_move = gets.chomp.to_i
          end
          if (valid_move?(next_move) == false)  # If move is not a valid one
            puts "#{next_move} is not a valid position, please choose a position on the board:"
            next_move = gets.chomp.to_i
          end
        end

        @moves.push(next_move) # Add the move to the set of moves, push makes @moves become an array
        return next_move
      end
    end

    class Board
      attr_accessor :board, :taken_moves

      def initialize
        @board = ['', '', '', '', '', '', '', '', ''] # positions on the board
        @taken_moves = [] # the positions that have been chosen
      end

      def display
        puts "Here is the current game board:"
        puts "\t#{@board[0]}\t|\t#{@board[1]}\t|\t#{@board[2]}"
        puts "--------------------------"
        puts "\t#{@board[3]}\t|\t#{@board[4]}\t|\t#{@board[5]}"
        puts "--------------------------"
        puts "\t#{@board[6]}\t|\t#{@board[7]}\t|\t#{@board[8]}"
      end

      def update(number, letter)
        @taken_moves.push(number) # add the  position number to the list of taken moves
        board[number - 1] = letter # put the character of the player (X or O) into the position to be displayed on the board
      end
    end

    def valid_move?(move)
      return move.between?(1,9) # check if the position of the move chosen is between 1 and 9
    end

    def move_taken?(move, taken_moves)
      move_taken = false # create a boolean variable to say whether the move is taken or not
      taken_moves.each do |item| # iterate through each member of the taken moves list, calling each member item
        if move == item # compare move to item
          move_taken = true
        end
      end
      return move_taken
    end

    def player_win?(player, winning_combos)
      winning_combos.each do |array|
        if player.moves.include?(array[0]) && player.moves.include?(array[1]) && player.moves.include?(array[2])
          # if the list of chosen moves by the player include one of the winning combos display winning message
          puts "Game over: #{player.name} wins!"
          player.score += 1
          return true
        end
      end
      return false
    end

    def draw?(game_board)
      # if the amount of moves taken is the same as the number of positions on the board then it's a draw
      if game_board.taken_moves.length >= game_board.board.length
        puts "Game over: Draw!"
        return true
      else
        return false
      end
    end

    def play_game(player1, player2)
      game_board = Board.new # Create a new board for the players to play on
      # the list of possible winning combos
      winning_combos = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [1, 4, 7], [2, 5, 8], [3, 6, 9], [1, 5, 9], [3, 5, 7]]
      player1.moves = [] # list of moves of each player
      player2.moves = []

      game_in_progress = true # set whether or not the game is in progress
      game_board.display # display the current state of the board

      while game_in_progress
        # code to update the moves made by player1 include the code to check whether this player has won
        if game_in_progress
          game_board.update(player1.choose_move(game_board.taken_moves), "X")
          game_board.display

          if player_win?(player1, winning_combos) || draw?(game_board)
            game_in_progress = false
          end
        end

        # code to update the moves made by player2 include the code to check whether this player has won
        if game_in_progress
          game_board.update(player2.choose_move(game_board.taken_moves), "O")
          game_board.display

          if player_win?(player2, winning_combos) || draw?(game_board)
            game_in_progress = false
          end
        end
      end
      # display the scores
      puts "The current scores are:"
      puts "#{player1.name}: #{player1.score}, #{player2.name}: #{player2.score}"
    end

    def create_players
      player1 = Player.new("X") # Create new player X
      player2 = Player.new("O") # Create new player O

      # this code display an empty board
      puts "Here are the positions of game board:"
      puts "\t1\t|\t2\t|\t3"
      puts "--------------------------"
      puts "\t4\t|\t5\t|\t6"
      puts "--------------------------"
      puts "\t7\t|\t8\t|\t9"

      # this code will prompt the user to choose whether or not to continue playing after each game ended
      play_again = 'y'

      while play_again == 'y'
        play_game(player1, player2)
        puts "Do you want to play another game? Enter [y/n]"
        play_again = gets.chomp
      end

      puts "Game Ends"
    end

    create_players