# rock-paper-scissor-game
this is a simple beginner rock, paper, scissor game
#i have used the random module to choose computer rock,paper,scissor randomly
import random
# This function contains everything that makes this game run — it handles user input, computer choice, comparison, and scoring.
def play():
    # options → a list of the three valid moves.
    # score → a dictionary keeping track of both user and the computer’s scores.
    options=["rock","paper","scissor"]
    score={"you": 0,"computer": 0}

  # this is for instruction more user friendly
    print("=== rock, paper, scissor ===")
    print("type 'q' to quit.\n")

  # This creates an infinite loop that keeps the game running until the user types 'q' to quit
   # .lower() makes sure the input works even if you type “Rock” or “ROCK”.
    while True:
        user=input("choose rock, paper, or scissor: ").lower()
  # if user equal to q or press q it will print final score or print thanks for playing then break the code
        if user == "q":
            print("\nfinal score", score)
            print("thanks for playing!")
            break
   # if user type anything except options it will show invalid choice the code will ask to continue
        if user not in options:
            print("this is invalid choice!,try again\n")
            continue
   # computer will chose the randomly from options then it will show what it chose 
        comp = random.choice(options)
        print(f"computer choose: {comp}")
   # its the simple logic implementation if both matched it will show tie and set some conditions,if matched result is winner also score gradually increase
        if user == comp:
            print("its a tie!\n")
        elif (user == "rock" and comp == "scissor") or \
             (user == "paper" and comp == "rock") or \
             (user == "scissor" and comp == "paper"):
            print("you win!\n")
            score["you"] +=1
  # if condition doesn't matched it will show computer wins and comp score gradually increase 
        else:
            print("computer wins!\n")
            score["computer"] +=1
  # Only run play() if this file is executed directly (not imported as a module).It’s a common Python pattern to keep code organized.
if __name__=="__main__":
    play()
