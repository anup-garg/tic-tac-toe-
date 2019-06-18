
board=[" "]*9

def print_board():
   # print ("  |  |  ")
    print ("" +board[0]+" |"+ board[1]+ " | "+board[2])
    print ("--|--|--")
    print (""+board[3]+" |"+board[4]+" | "+board[5]+" ")
    print ("--|--|--")
    print (""+board[6]+" |"+board[7]+" | "+board[8]+" ")

    
#win cobination
def check_position():
    if(board[0]==board[1]==board[2]=="x" or board[0]==board[1]==board[2]=="o"):
        return 1
    elif(board[3]==board[4]==board[5]=="x" or board[3]==board[4]==board[5]=="o"):
        return 1    
    elif(board[6]==board[7]==board[8]=="x" or board[6]==board[7]==board[8]=="o"):
        return 1
    elif(board[0]==board[3]==board[6]=="x" or board[0]==board[3]==board[6]=="o"):
        return 1
    elif(board[1]==board[4]==board[7]=="x" or board[1]==board[4]==board[7]=="o"):
        return 1
    elif(board[2]==board[5]==board[8]=="x" or board[2]==board[5]==board[8]=="o"):
        return 1
    elif(board[0]==board[4]==board[8]=="x" or board[0]==board[4]==board[8]=="o"):
        return 1
    elif(board[2]==board[4]==board[6]=="x" or board[2]==board[4]==board[6]=="o"):
        return 1
    else:  
        return 2

def player1():
    choice = input("please choose an x in empty space")
    choice = int(choice)
    if(board[choice]=="x" or board[choice]=="0"):
        print("not empty")
        player1()
    else:
              board [choice] = "x"
              
def player2():
    choice = input("please choose an o in empty space")
    choice = int(choice)
    if(board[choice]=="x" or board[choice]=="0"):
       print("not empty")
       player2()
    else:
              board [choice] = "o"
              
print_board()
x=2
while(x==2):
    player1()
    x=check_position()
    print_board()
    if(x==1):
        print("x is win")
        break
    player2()
    x=check_position()
    print_board()
    if(x==1):
        print("o is win")
        break
    

