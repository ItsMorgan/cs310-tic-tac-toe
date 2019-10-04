INTRODUCTION

This Java application is a game where two users take turns marking squares with either an 'X' or an 'O'. The winner is determined by which
player succeeds in having the number of marked squares in a row, equal to the size of the game board. If each square on the board is marked,
and there is no winner, the result is a tie. The default size of the board is 3x3. The size may be changed by entering the following
into the command prompt: 

        java -jar TicTacToe.jar

For example, to change the board to an 8x8, enter '8' at the end of the command, like so: 

        java -jar TicTacToe.jar 8

This program contains five classes: TicTacToe, TicTacToeController, TicTacToeModel, TicTacToeMove, and TicTacToeMove

TicTacToe (main file) and TicTacToeController (controller)
        After the user enters the size of the board, the model (TicTacToeModel) and the view (TicTacToeView) are initialized.
        After this, the controller calls the function called "start()". Next, a loop begins, which tests whether the game is over, 
        and the view's "toString()" function is executed. The player's next move is entered and retrieved by the "getNextMove" function
        in the view. This function retrives the user's input and uses a boolean to determine which player is making the move. The boolean
        is true for player one (X) and false for player two (O). The player's move is then added to the board. If the user's input is invalid,
        an error is displayed by the view. Retrieving the user's input, determining which user is placing their move, and adding their move
        to the game board is repeated until the "isGameOver" boolean is switched to true. The boolean is activated by a winner or a tie,
        then the game board displays the results.

TicTacToeView (view) and TicTacToeMove (move
        The view file handles the input and output for the program. When the view is initialized, a scanner is assigned to a variable
        for assisting with further input from the keyboard. Next, an if statement outputs which player's turn it is by displaying
        "Player 1 (X) Move:" or "Player 2 (O) Move" depending on which turn was last. If it is the first turn, then player one begins. 
        
       

