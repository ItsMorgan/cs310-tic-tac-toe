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

TicTacToeView (view) and TicTacToeMove (move)
        The view file handles the input and output for the program. When the view is initialized, a scanner is assigned to a variable
        for assisting with further input from the keyboard. Next, an if statement outputs which player's turn it is by displaying.
        "Player 1 (X) Move:" or "Player 2 (O) Move" depending on which turn was last. If it is the first turn, then player one begins. Next, the following instructions are displayed: "Enter the row and column numbers, separated by a space:". The user's input from the keyboard is then recorded. Checking for errors in the user's input begins here by separating the two colums by splitting the string, using a space as the delimiter. The two strings are now in an array, so each string in the array is checked to ensure the characters are integers and that there are only two strings in the array. If these tests are passed, the two strings are parsed into coordinates of the player's selection and are stored in the "TicTacToeMove" class. This class stores the coordinates for further use in the Model class. The remainder of "TicTacToeView" contains a function for error printing. An error message that says "Entered location is invalid, alreqady marked, or out of bounds" is displayed if an error is detected. Also included in the View is a function that is called to display the winner of the game, but it requires the player's name ("X" or "O") as its parameters. The last function in the View prints the game board when called.
        
TicTacToeModel (model)
        The model is essentially the brain of the program, so this class contains many components. Many varibles are declared in the beginning of this class including the board size, a boolean to determine which player's turn is next, and the board which is a two dimensional array of marks. A mark is a variable matched to a string, but it is declared in a separate function which can be called to retrieve those strings. The specific strings in the function are "X", "O", and "-". By using the same method, the results of the game after completion are stored. In the constructor of the model, the board size is checked, then the boolean that decides which player's turn is next is switched to player one because this is the first turn. Next, the two dimensional array of marks is declared using the board size to set the length of the rows and columns. A nested for loop fills each space in the array with "-" marks. The "makeMark()" function is used for making a mark on the game board by accepting a row and column number which is equivalent to the X and Y in a graph. This function further checks the player's selection by using the "isValidSquare()" and "isSquareMarked()" functions. It also checks that the mark is within the bounds of the board, after validating the player's selection. The second function checks space being marked is empty or contains the mark of another player. If the player's mark passes all the checks, then the function marks the board with an "X" or an "O" based on which player's turn it is. Additionally, the "getMark()" function returns the mark requested in the parameters. The "isTurn()" function returns a boolean indicating which player is playing, and the "getWidth()" function returns the size of the game board.
        
To determine a Winner, the. "getResult()" function is called by the "isGameOver()" function in the controller. The "getResult()" function returns the results: "X, O, TIE or NONE" based on two other functions called "isMarkWin()" and "isTie()." These two functions contain the code for setting the win and tie conditions. By using nested if statements inside nested for loops, each square in the game board is checked from left to right, then up to down. When the row and column numbers equal the number of times in the board size in a row, a right diagonal win condition is met. When the row and column numbers added to each other equal one subtracted by the board size as manytimes as the board size in a row, a left diagonal win condition is met. The horizontal and vertical counters are set as the diagonals are being tested. A counter is addedto the vertical or horizontal variables if there are any of the same row numbers or column numbers. A horizontal or vertical win condition is met when the number of identical row numbers and column numbers equal the size of the game board. The "isTie()" function allows the game board to be iterated through, and if there are no empty spaces or winners, TRUE is returned to indicate a TIE.

The game board is constructed in the "toString()" method of the Model. The main components of this function are String Builders. The column headers are appended here by a for loop. After this, a new line is added and a nested for loop iterates through the game board and appends each row at a time from left to right by adding the row number, row marks then another new line. A new line is also added before the string is returned.

Here is example output from this program:

        Player 1 (X) Move:
	Enter the row and column numbers, separated by a space: 1 1

	  012
	0 -X-
	1 -XO
	2 ---

	Player 2 (O) Move:
	Enter the row and column numbers, separated by a space: -1 2
	Entered location is invalid, already marked, or out of bounds.


	  012
	0 -X-
	1 -XO
	2 ---

	Player 2 (O) Move:
	Enter the row and column numbers, separated by a space:


