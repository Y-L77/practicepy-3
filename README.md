import random

#this python practice exercises manipulating lists, loops & functions

words = ["CATERPILLAR", "COFFEE", "JAVASCRIPT", "CYBERSECURITY", "WATERSLIDE", "CHINA", "MOOSE"]
GUESSWORD = random.choice(words)
characters = len(GUESSWORD)
underscores = "_" * characters
guessed_letters = set()

def display_word(word, guessed_letters):
    display = ""
    for letter in word:
        if letter in guessed_letters:
            display += letter
        else:
            display += "_"
    return display

def userguess():
    return input("What is your guess? ").upper()

print("Welcome to Guess the Word! You have 3 guesses.")
print(display_word(GUESSWORD, guessed_letters))

for i in range(3):
    guess = userguess()
    guessed_letters.add(guess)

    if guess == GUESSWORD:
        print("Correct!")
        break
    else:
        print("Incorrect.")
        if i < 2 and guess != GUESSWORD:
            print("Try again.")
        print(display_word(GUESSWORD, guessed_letters))
else:
    print("Sorry, you're out of guesses. The word was:", GUESSWORD)
