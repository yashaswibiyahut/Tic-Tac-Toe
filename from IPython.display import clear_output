from IPython.display import clear_output
import random

def display_board(board):                                         # Clears previous and displays game board
    clear_output()
    print('{}|{}|{}'.format(board[7],board[8],board[9]))
    print('{}|{}|{}'.format(board[4],board[5],board[6]))
    print('{}|{}|{}'.format(board[1],board[2],board[3]))
    
def player_input():                                                # Players pick X or O returns tuple
    while(True):
        p1 = input("Please pick a marker 'X' or 'O'")
        p2 = ''
        if p1.lower() == 'x' or p1.lower() == 'o':
            break          
    if p1.lower() == 'x':
        p2='O'
        print('------------------------------------------------------------------')
        print('Player 1 is {} and Player 2 is {}'.format(p1.upper(),p2.upper()))
    elif p1.lower() == 'o':
        p2='X'
        print('------------------------------------------------------------------')
        print('Player 1 is {} and Player 2 is {}'.format(p1.upper(),p2.upper()))
        
    return (p1.upper(),p2.upper())    
    
def place_marker(board, marker, position):                          # Appends list position of new marker 
    board[position] = marker
    
def win_check(board, mark):                                          # Check to see if game is won 
    if board[1] == board[2] == board[3] == mark:
        return True
    elif board[1] == board[4] == board[7] == mark:
        return True
    elif board[1] == board[5] == board[9] == mark:
        return True
    elif board[2] == board[5] == board[8] == mark:
        return True
    elif board[3] == board[5] == board[7] == mark:
        return True
    elif board[3] == board[6] == board[9] == mark:
        return True
    elif board[4] == board[5] == board[6] == mark:
        return True
    elif board[7] == board[8] == board[9] == mark:
        return True
    else:
        return False
      
 def choose_first():                                                  # Picks on random which player goes first 
    return 'Player {} goes first'.format(random.randint(1,2))
    
def space_check(board, position):                                     # Identifies if the selected space is chosen or not
    if board[position] == ' ':
        return True
    else:
        return False
       
def full_board_check(board):                                           # Checks if board is full and the game is a draw
    for i in range(1,len(board)):
        if board[i] == ' ':
            return False
        elif board[i] != ' ':
            continue 
    return True
        
def player_choice(board):                                               # Inputs player position
    while(True):
        position = input('Enter next position number 1-9: ')
        if str(position) in '1,2,3,4,5,6,7,8,9' and space_check(board,int(position)) == False:
            continue
        elif str(position) in '1,2,3,4,5,6,7,8,9' and space_check(board,int(position)) == True:
            return int(position)
        else:
             continue    
             
def replay():                                                             # Prompt for a replay
    while(True):
        replay = input('Do you want to play again? Yes or No?')
        if replay.lower() == 'yes':
            return True
        elif replay.lower() == 'no':
            return False 
        else:
            continue 
            
def game():                                                                 # Main compilation of game
  while True:
    board = [' ',' ',' ',' ',' ',' ',' ',' ',' ',' ']
    print('Welcome to Tic Tac Toe!')
    game_on = True
    (p1,p2) = player_input()
   
    while game_on:
        print('{} goes first'.format(choose_first()))
        
        # Player1's turn.
        position = player_choice(board)
        place_marker(board,p1,position)
        display_board(board)
        if win_check(board, p1) == True:
            print('player 1 won the game')
            break
        elif full_board_check(board) == True:
            print("Game draw")
            break
        
        # Player2's turn.
        position = player_choice(board)
        place_marker(board,p2,position)
        display_board(board)
        if win_check(board, p2) == True:
            print('player 2 won the game')
            break
        elif full_board_check(board) == True:
            print("Game draw")
            break
            
    if replay() == True:
        continue
    else:
        break
         
 game()
