﻿import random

def print\_board(board): for row in board: print(" | ".join(row)) print("-" \* 9) def is\_winner(board, player):

for i in range(3): ![](Aspose.Words.51e8cf15-d8c3-44b7-9206-3f2e25328363.001.png)

`    `if all(board[i][j] == player for j in range(3)) or all(board[j][i] == player for j in range(3)): 

`        `return True 

if all(board[i][i] == player for i in range(3)) or all(board[i][2 - i] == player for i in range(3)): 

`    `return True 

return False

def is\_board\_full(board): return all(board[i][j] != ' ' for i in range(3) for j in range(3))

def get\_empty\_cells(board): return [(i, j) for i in range(3) for j in range(3) if board[i][j] == ' ']

def minimax(board, depth, maximizing\_player): if is\_winner(board, 'X'): return -1 elif is\_winner(board, 'O'): return 1 elif is\_board\_full(board): return 0

if maximizing\_player: ![](Aspose.Words.51e8cf15-d8c3-44b7-9206-3f2e25328363.002.png)

`    `max\_eval = float('-inf') 

`    `for i, j in get\_empty\_cells(board): 

`        `board[i][j] = 'O' 

`        `eval = minimax(board, depth + 1, False)         board[i][j] = ' ' 

`        `max\_eval = max(max\_eval, eval) 

`    `return max\_eval 

else: 

`    `min\_eval = float('inf') 

`    `for i, j in get\_empty\_cells(board): 

`        `board[i][j] = 'X' 

`        `eval = minimax(board, depth + 1, True)         board[i][j] = ' ' 

`        `min\_eval = min(min\_eval, eval) 

`    `return min\_eval

def get\_best\_move(board): best\_val = float('-inf') best\_move = None for i, j in get\_empty\_cells(board): board[i][j] = 'O' move\_val = minimax(board, 0, False) board[i] [j] = ' ' if move\_val > best\_val: best\_val = move\_val best\_move = (i, j) return best\_move

def play\_game(): board = [[' ' for \_ in range(3)] for \_ in range(3)] while not is\_winner(board, 'X') and not is\_winner(board, 'O') and not is\_board\_full(board): print\_board(board) player\_move = tuple(map(int, input("Enter your move (row and column): ").split())) if board[player\_move[0]][player\_move[1]] == ' ': board[player\_move[0]][player\_move[1]] = 'X' else: print("Invalid move. Try again.") continue

`    `if is\_winner(board, 'X'):  ![](Aspose.Words.51e8cf15-d8c3-44b7-9206-3f2e25328363.003.png)       print\_board(board) 

`        `print("You win!") 

`        `break 

`    `if is\_board\_full(board):         print\_board(board) 

`        `print("It's a tie!")         break 

print("Computer's move:") 

computer\_move = get\_best\_move(board) board[computer\_move[0]][computer\_move[1]] = 'O' 

`    `if is\_winner(board, 'O'): 

`        `print\_board(board) 

`        `print("Computer wins!")         break 

`    `if is\_board\_full(board):         print\_board(board) 

`        `print("It's a tie!")         break

if **name** == "**main**": play\_game() 
**output** 



![image](https://github.com/user-attachments/assets/bfb2172b-cf72-4828-975d-b05e8e5b9116)

