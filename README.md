# number-guessing-game

import random as r
import math as m

def level_one() :
    n = r.randint(1,100)
    count = 1
    point = 100
    print('\t\t\t\tLEVEL ONE\n\t\tYOU HAVE 10 CHANCES!!! ALL THE BEST')
    while count < 10 :
        guess = int(input(f'Guess {count} : '))
        if(guess == n) :
            print(f"\nCONGATULATIONS {name}!!! You've done it... \n\tYou have won the game in {count-1} chances!!!!")
            print(f'\t\t\tTOTAL POINTS : {point}')
            a = input('Are you ready for level two??')
            return a,point
        elif(guess < n) :
            print(f"\nSorry {name}! You've guessed it too low! \n\t\tTRY AGAIN!!")
            point-=10
        else :
            print(f"\nSorry {name}! You've guessed it too high! \n\t\tTRY AGAIN!!")
            point-=10
        count+=1
    if(count > 10) :
        print(f"\nOOPS!! YOU'VE LOST IT!!!")
        print(F"The number was : {n}\n\t\tTOTAL POINTS : {point}")
        print("BETTER LUCK NEXT TIME!")
        b = input("Do you want to play again???")
        if(b=='yes') :
            level_one()
        else :
            print("\nTHANK YOU FOR PLAYING!!")

def level_two(point) :
    n = r.randint(1,100)
    print(n)
    count = 1
    print('\t\t\t\tLEVEL TWO\n\t\tYOU HAVE 5 CHANCES...ALL THE BEST!!')
    
    while count <= 5 :
        guess = int(input(f'Guess {count} : '))
        if(guess == n) :
            print(f"\nCONGATULATIONS {name}!!! You've done it... \n\tYou have won the game in {count} chances!!!!")
            print(f'\t\t\tTOTAL POINTS : {point}')
            a = input('Do you want to play again??')
            if(a == 'yes') :
                level_one()
            else :
                break
        elif(guess < n) :
            print(f"\nSorry {name}! You've guessed it too low! \n\t\tTRY AGAIN!!")
            point-=10
        else :
            print(f"\nSorry {name}! You've guessed it too high! \n\t\tTRY AGAIN!!")
            point-=10
        count+=1
    if(count > 5) :
        print(f"\nOOPS!! YOU'VE LOST IT!!!")
        print(F"The number was : {n}\n\t\tTOTAL POINTS : {point}")
        print("BETTER LUCK NEXT TIME!")
        b = input("Do you want to play again???")
        if(b=='yes') :
            level_one()
        else :
            print("\nTHANK YOU FOR PLAYING!!")


name = input('Enter your name : ')
print(f"Hello {name}!")
point = 100
print("Welcome to the Number Guessing Game !!")
print("General Games Rules : \n\tYou will have a total of 100 points at the start")
print("\tThe game conists of 2 levels\n\tEach level has one number to guess\n\tAfter each wrong guess 10 points will be deducted\n\tBut don't worry, A clue will be provided after each wrong guess!!!")
print("\tFirst level has 10 chances \n\tSecond level has 5 chances")
y = input("\nAre you ready???")
if(y == 'yes'):
    x,p = level_one()
    if(x == 'yes') :
        level_two(p)
    else :
        print("\nTHANK YOU FOR PLAYING!!")

