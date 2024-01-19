from random import randint
import time

list = ["rock", "paper", "scissors"]

state = {"state": 0,
        "winner": ""}

def start():
    
    while state["state"] == 0:
        try:
            print("\nWelcome to play rock, paper, scissors!")
            print("Can you beat the computer?")
                    
            print("\nLets start! What would you like to do?")   
            print("[1] Start game")
            print("[2] Check your stats")
            print("[3] End game")
            
            choice = int(input("Give your choice number [1-3]: "))
            if choice < 1 or choice > 3:
                print("That is not valid, please, give a number between 1-3.\n")
        except ValueError:
            print("You gave an invalid value, please enter your choice as an integer.\n") 
        
        if choice == 1:
            state["state"] = 1
        elif choice == 2:
            with open("rps_document.txt", "r") as file:
                for row in file:
                    print(row)
        elif choice == 3:
            state["state"] = 3
            exit()  
                    
    while state["state"] == 1:
        
        print("\nHow do you play?")
        print("Your opponent is a computer, which takes a random choice in each round.")
        print("The winner is the one who gets tree wins first.")
        print("You can choose either rock, paper or scissors by writing r, p or s.")
        print("-------------------------------------------------------------------")
        game()

def game():
    win_c = 0
    win_p = 0
                
    while (win_c < 3 and win_p < 3):
        computer = list[randint(0,2)]
        game = input("\nrock, paper, scissors? ").lower()
            
        if game == "r":
            choice = "rock"
        elif game == "rock":
            choice = "rock"
            
        elif game == "p":
            choice = "paper"
        elif game == "paper":
            choice = "paper"
            
        elif game == "s":
            choice = "scissors"
        elif game == "scissors":
            choice = "scissors"
            
        else:
            choice = "invalid"
            
        if choice == computer:
            print("Tie! Both choose " + choice + ".")
            print("-----------------------------------")

        elif choice == "rock":
            if computer == "paper":
                print('Computer: ' + computer)
                print("\nYou lost! Paper beats rock.")
                win_c += 1
                print("You " + str(win_p) + " - " + str(win_c) + " Computer")
                print("-----------------------------------")
                

            else:
                print('Computer: ' + computer)
                print("\nYou won! Rock beats scissors.")
                win_p += 1
                print("You " + str(win_p) + " - " + str(win_c) + " Computer")
                print("-----------------------------------")
                 
        elif choice == "paper":
            if computer == "scissors":
                print('Computer: ' + computer)
                print("\nYou lost! Scissors beats paper.")
                win_c += 1
                print("You " + str(win_p) + " - " + str(win_c) + " Computer")
                print("-----------------------------------")
               
            else:
                print('Computer: ' + computer)
                print("\nYou won! Paper beats rock.")
                win_p += 1
                print("You " + str(win_p) + " - " + str(win_c) + " Computer")
                print("-----------------------------------")
                  
        elif choice == "scissors":
            if computer == "rock":
                print('Computer: ' + computer)
                print("\nYou lost! Rock beats scissors.")
                win_c += 1
                print("You " + str(win_p) + " - " + str(win_c) + " Computer")
                print("-----------------------------------")
              
            else:
                print('Computer: ' + computer)
                print("\nYou won! Scissors beat paper.")
                win_p += 1
                print("You " + str(win_p) + " - " + str(win_c) + " Computer")
                print("-----------------------------------")
                  
        elif choice == "invalid":
            print("That's not rock, paper or scissors, please choose again.")
               
        if win_p == 3:
            state["winner"] = "player"
        elif win_c == 3:
            state["winner"] = "computer"   
               
        computer = list[randint(0,2)]  
        state["state"] = 0
    
def save_stats(name):

    date = time.asctime()
    winner = state["winner"]
    
    with open(name, "a") as file:
       file.write("Game was played: {date}, winner: {winner}\n".format(
            date=date,
            winner=winner))
       
if __name__ == "__main__":  
    
    while state["state"] != 3:
        
        start()
        save_stats("rps_document.txt")    
