# Thinking in Objects
With the knowledge of basic __object oriented programming__, it's time for us to start thinking about programs that we are going to write in an __object oriented__ way.
* In a nutshell, an OOP application is just a bunch of objects created from one or various classes interact with each other.

However, you have to be able to **identify the right classes and the right methods** which those classes will have in order to create a functional application.

## Design
The first thing you should always do before start writing your code is to design the project, in this case, design the game.
**Note:** In reality the processes that you have to go through beforehand are the most time consuming and complex. The easiest part of application development is actually writing the code.

__**Extra Note:**__ If you haven't heard of [Tic Tac Toe](https://en.wikipedia.org/wiki/Tic-tac-toe).

### Identify the classes
Since we are creating a TicTacToe game, let's try and identify the classes that will be present in the game.

* __Board:__ When we start a new game, we're creating an instance of class `Board`
* __Player:__ A game will need someone to play it right? Therefore we will need a class Player which will interact with the class Game.

The game of TicTacToe is a game between 2 people but that doesn't mean we have to create 2 different player classes, instead we create 2 instances of class Player.
Pretty straightforward isn't it? Let's move on.

### Identify the classes' methods
So we've established that we need **Game and Player** classes in order to create this program, we also know the properties each class should have. Now, let's try and figure out what functions (methods) that each class should possess.

* __Board:__ If you think about it, in this program the __Board__ is a board and it holds a list of positions on the board, mark the positions as taken and display it to the player. Therefore, we will have an __initialize__ method, a __display__ method to display the content of the board and an __update__ method to update the state of the game.
* __Player:__ A player in this case can choose a move and that's it. Therefore we will have a function to create __initialize__ a player and a function to choose the move, let's be creative and call it __choose_move__.

After we're happy with our design, it's HAMMER TIME!!! Just kidding, it's time to write some code.

## Scaffolding
Now that we know what to do, let's try to scaffolding our program (Programming is just like building a house isn't it?). This is the process of writing out the classes, their properties and functions.

### Board
A game of TicTacToe are mostly played on a 3x3 board so we have an instance `@board` which is an array of positions on the board. In order to keep track of the moves that have been chosen by the players, we have another array `@taken_moves`.
Regarding the methods, __initialize__ should set the board of 3x3 (=9) to empty in each position and the array of taken moves to be empty.
__update__ will take in the position number and the player's letter (X or O) and update it to the `board`.
__display__ is going to display the state of the board.

__**Note:**__ In this program and from now on, we are going to start using *attr_accessor*. Don't worry, it's just a short way to declare getter and setter methods for our variables.

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

### Player
A player will have a name (X or O), the move they make and their score. They can choose a move so we create a function __choose_move__ that takes in 1 parameter that is the move taken by the player. Finally, a Player is __initialize__ with a name, this name is the thing that set 2 players apart.

    class Player
      attr_accessor :name, :moves, :score

      def initialize(name)
        # Code
      end

      def choose_move(taken_moves)
        # Code
      end
    end

And that's the outline of what we need for our TicTacToe game.

## Task
>1. Scaffold the Quiz game in Challenge 1
>2. Create an Object Oriented version of the Quiz Game
