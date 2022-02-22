![1_2KdEtbQJbX6r-ARyM1smSA](https://user-images.githubusercontent.com/79866006/155039005-16850ab5-9395-4c17-a89e-e80de4f4a150.png)


# Hangman Game Python Version 

The origins of Hangman are obscure meaning not discovered, 
but it seems to have arisen in Victorian times, ” says Tony Augarde, author of The Oxford Guide to Word Games.
The game is mentioned in Alice Bertha Gomme’s “Traditional Games” in 1894 under the name “Birds, Beasts and Fishes.” 
The rules are simple; a player writes down the first and last letters of a word and another player guesses the letters in between.
In other sources, the game is called “Gallows”, “The Game of Hangin”, or “Hanger”.


This is a simple Hangman game using Python programming language. 
Beginners can use this as a small project to boost their programming skills and understanding logic.

# Code Review 
### NOTE 
>> Run the program on your terminal.
>> 
>> Use the latest version of python. Python v3.8 and above
To Check your python version:

run 'python --version' in your command line either (Windows), shell (Mac), or terminal (Linux/Ubuntu). 
To check your Python version in your script, run 'import sys' to get the module and use 'sys.version' to find detailed version information in your code.

'''
>>> import sys
>>> sys.version
'3.9.10 (v3.9.10:d047928ae3f6, Febuary 22 2022, 00:06:53) '
'''

# 
[^1]: Import the random module.

'''
 import random 

from collections import Counter 
'''

[^2]: Here, a random word (a fruit name) is picked up from the collections.

'''
#######
'''

[^3]: For printing the empty spaces for letters of the word 

'''
     # For printing the empty spaces for letters of the word 

        print('_', end = ' ')

    print() 

  

    playing = True
'''

[^4]: For convenience, we have given length of word + 2 chances. 
In this way, all letters of the word are to be guessed before all the chances are over.

'''
     # list for storing the letters guessed by the player 

    letterGuessed = ''                 

    chances = len(word) + 2

    correct = 0

    flag = 0

    try: 

        while (chances != 0) and flag == 0: #flag is updated when the word is correctly guessed  

            print() 

            chances -= 1
'''

[^5]: We create a decision-making process, to check that the user only enters alphabets and not numbers as a name.

'''
try: 

                guess = str(input('Enter a letter to guess: ')) 

            except: 

                print('Enter only a letter!') 

                continue

  

            # Validation of the guess 

            if not guess.isalpha(): 

                print('Enter only a LETTER') 

                continue

            elif len(guess) > 1: 

                print('Enter only a SINGLE letter') 

                continue

            elif guess in letterGuessed: 

                print('You have already guessed that letter') 

                continue
'''

[^6]: When a letter in that word is guessed correctly, that letter position in the word is made visible. 

'''

            if guess in word: 

                k = word.count(guess) #k stores the number of times the guessed letter occurs in the word 

                for _ in range(k):     

                    letterGuessed += guess # The guess letter is added as many times as it occurs 

  

            # Print the word 

            for char in word: 

                if char in letterGuessed and (Counter(letterGuessed) != Counter(word)): 

                    print(char, end = ' ') 

                    correct += 1

                # If user has guessed all the letters 

                elif (Counter(letterGuessed) == Counter(word)): # Once the correct word is guessed fully,  

                                                                # the game ends, even if chances remain 

                    print("The word is: ", end=' ') 

                    print(word) 

                    flag = 1

                    print('Congratulations, You won!') 

                    break # To break out of the for loop 

                    break # To break out of the while loop 

                else: 

                    print('_', end = ' ') 

'''

[^7]: If user use all of chances 

'''

  

        # If user has used all of his chances 

        if chances <= 0 and (Counter(letterGuessed) != Counter(word)): 

            print() 

            print('You lost! Try again..') 

            print('The word was {}'.format(word)) 
            
            print()
            
            # autor contact
            print('Contact TYP for more programming code')
            
            print('Search Google for :')
            
            print ('The Young Programmer Nemonet')

'''

[^8]: To exit the game 

'''

    except KeyboardInterrupt: 

        print() 

        print('Bye! Try again.') 

exit()

'''

# Code Demo:

'''
Guess the word! HINT: word is a name of a fruit
_ _ _ _ 

Enter a letter to guess: m
_ _ m _ 
Enter a letter to guess: i
_ i m _ 
Enter a letter to guess: l
l i m _ 
Enter a letter to guess: e
l e m e
Congratulations, You won!
'''



