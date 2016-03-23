# Skeleton of Tic Tac Toe

## Unfinished Business
Through planning, we've identified the necessary classes and their function, when put everything together we should have the following: __Save this as tictactoe.rb__

    class Player
      attr_accessor :name, :moves, :score

      def initialize(name)
        # Code
      end

      def choose_move(taken_moves)
        # Code
      end
    end

    class Board
      attr_accessor :board, :taken_moves

      def initialize
        # Some Code
      end

      def display
        # Some code here
      end

      def update(number, letter)
        # Some code here
      end
    end
## Logic not Logical
Now, having just these 2 classes wouldn't complete our game. Firstly because this we haven't got any actual code or logic in our program. Secondly, we haven't got a way to make the 2 classes interact with each other. So let's resolve these 2 problems.

So the logic of this game is as follow:
* Create a game with 2 players
* While the game is not finish:
    * Display the board
    * The first player chooses their move
    * The game check whether the move chosen by the player is valid. If move is valid, update the board. If not, prompt the player to choose their move again.
    * Check whether the player has won or the board has been filled. If true, end the game.
* Announce the winner and display the scores.

## Help!!!
Based on the logic of the game, we need some "helper functions" to help us tying the the object interactions together.

    def valid_move?(move)
      # Code
    end

    def move_taken?(move, taken_moves)
      # Code
    end

    def player_win?(player, winning_combos)
      # Code
    end

    def draw?(game_board)
      # Code
    end

    def play_game(player1, player2)
      # Code
    end

    def create_players
      # Code
    end

Let's walk through these functions step by step:

* __valid_move?(move):__ This function takes in a move which is just a number representing the position on the board and check whether or not it's a valid move. For example: __valid_move(2)__ will return __true__ but __valid_move(10)__ will return __false__.
* __move_taken?(move, taken_moves):__ This function takes in the move made by the player and the list of moves that have been made by each player since the start of the game and check whether `move` is in the list `taken_moves`.
* __player_win?(player, winning_combos):__ This function takes in the player (there are 2 players) and check whether the moves taken by them match with one of the winning combos. An example of a winning combo is "1, 2, 3".
* __draw?(game_board):__ This function check if the board has been filled.
* __play_game(player1, player2):__ This function create an instance of class __Board__ with the 2 players. Then it follows the logic stated in the previous part.
* __create_players:__ This is the function which will create 2 instances of class __Player__ and display the initial configuration of the board.

So, putting all this together, our __tictactoe.rb__ file should look like so:

    class Player
      attr_accessor :name, :moves, :score

      def initialize(name)
        # Code
      end

      def choose_move(taken_moves)
        # Code
      end
    end

    class Board
      attr_accessor :board, :taken_moves

      def initialize
        # Some Code
      end

      def display
        # Some code here
      end

      def update(number, letter)
        # Some code here
      end
    end

    def valid_move?(move)
      # Code
    end

    def move_taken?(move, taken_moves)
      # Code
    end

    def player_win?(player, winning_combos)
      # Code
    end

    def draw?(game_board)
      # Code
    end

    def play_game(player1, player2)
      # Code
    end

    def create_players
      # Code
    end

    create_players # this line is used to automatically start the game when the file is run.

## Task
Using what you've learned and good ol' Google, try your best to complete the game of Tic Tac Toe. __Good Luck!!!__