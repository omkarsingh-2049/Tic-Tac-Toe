# Tic-Tac-Toe Game

A simple **2-player console-based Tic-Tac-Toe game** written in **C++**. The game uses a 3×3 board where two players take turns placing `X` and `O` until one player wins or the game ends in a draw.

The program also supports replaying the game after each round.

## Features

- 2-player Tic-Tac-Toe game
- 3×3 game board
- Player `X` starts the game
- Players take turns between `X` and `O`
- Position-based moves using numbers `1-9`
- Automatic win detection
- Draw detection
- Invalid move handling
- Replay option after a game ends
- Simple console-based interface

## Technologies Used

- **Language:** C++
- **Library:** `iostream`
- **Interface:** Console / Command Line

## Project Structure

```text
TicTacToe/
│
├── TicTacToe.cpp
└── README.md
```

## How to Play

The game board is represented using positions from `1` to `9`:

```text
 1 | 2 | 3
---|---|---
 4 | 5 | 6
---|---|---
 7 | 8 | 9
```

Players select the number of the position where they want to place their symbol.

For example:

- Player `X` enters `1` → `X` is placed in the top-left position.
- Player `O` enters `5` → `O` is placed in the center.

A player wins by placing three of their symbols in:

- Any horizontal row
- Any vertical column
- The main diagonal
- The opposite diagonal

## Game Flow

1. The board is initialized with positions `1-9`.
2. Player `X` makes the first move.
3. Players alternate between `X` and `O`.
4. After every move, the program checks whether the current player has won.
5. If there is no winner, the program checks whether the board is full.
6. The game ends when:
   - A player wins, or
   - The game is a draw.
7. The user is asked whether they want to play again.

## Main Functions

### `initBoard()`

Initializes the 3×3 board with position numbers from `1` to `9`.

```cpp
void initBoard()
```

### `displayBoard()`

Displays the current game board in a readable 3×3 format.

```cpp
void displayBoard()
```

### `checkWin(char player)`

Checks all rows, columns, and both diagonals to determine whether the specified player has won.

```cpp
bool checkWin(char player)
```

### `isDraw()`

Checks whether all positions on the board are occupied by either `X` or `O`.

```cpp
bool isDraw()
```

### `makeMove(int choice, char player)`

Converts a selected position from `1-9` into a row and column and places the player's symbol on the board.

If the selected position is already occupied, the program displays an invalid-move message and asks for the move again.

```cpp
void makeMove(int choice, char player)
```

## How to Compile and Run

### Using g++

Compile the program:

```bash
g++ TicTacToe.cpp -o TicTacToe
```

Run on Windows:

```bash
TicTacToe.exe
```

Run on Linux/macOS:

```bash
./TicTacToe
```

### Using VS Code

1. Install a C++ compiler such as **MinGW** on Windows or **G++** on Linux.
2. Open the project folder in VS Code.
3. Open the integrated terminal.
4. Compile the program:

```bash
g++ TicTacToe.cpp -o TicTacToe
```

5. Run the generated executable.

## Example Gameplay

```text
 1 | 2 | 3
---|---|---
 4 | 5 | 6
---|---|---
 7 | 8 | 9

Player X, enter position (1-9): 1

 X | 2 | 3
---|---|---
 4 | 5 | 6
---|---|---
 7 | 8 | 9

Player O, enter position (1-9): 5
```

The game continues until a player wins or all positions are filled.

At the end of the game:

```text
Player X wins!
```

or:

```text
It's a draw!
```

The program then asks:

```text
Play again? (y/n):
```

## Concepts Demonstrated

### 2D Arrays

The game board is stored using a two-dimensional character array:

```cpp
char board[3][3];
```

### Functions

The program is divided into separate functions for board initialization, display, move handling, win checking, and draw detection.

### Conditional Statements

`if` statements are used to determine:

- Whether a move is valid
- Whether a player has won
- Whether the game is a draw

### Loops

The program uses loops to:

- Initialize and display the board
- Check winning conditions
- Check for a draw
- Continue the game until it ends
- Allow replaying the game

### Recursion

The `makeMove()` function calls itself when a player selects an occupied position, allowing the player to try again.

## Current Limitations

- Supports only two human players
- No single-player mode against computer AI
- No difficulty levels
- Input validation is limited for invalid numbers outside the expected `1-9` range
- No score tracking across multiple rounds
- No graphical user interface
- The game state is not saved to a file

## Possible Future Improvements

- Add a single-player mode with AI
- Add multiple AI difficulty levels
- Add score tracking for `X` and `O`
- Improve input validation for non-numeric input
- Add customizable player names
- Add a graphical user interface (GUI)
- Add sound effects and animations
- Add persistent match statistics

## Author

**Devarshi Gautam**

## License

This project is intended for educational and learning purposes.
