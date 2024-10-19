import random

# List of words for the game
words = ['python', 'developer', 'code', 'program', 'algorithm', 'function', 'variable', 'debug']

# Function to choose a random word
def get_random_word(word_list):
    return random.choice(word_list)

# Main game function
def play_game():
    word = get_random_word(words)
    guessed_word = ['_'] * len(word)
    attempts = 6
    guessed_letters = []

    print("Welcome to the Word Guessing Game!")
    print(f"Guess the word: {' '.join(guessed_word)}")

    while attempts > 0 and ''.join(guessed_word) != word:
        guess = input("\nGuess a letter: ").lower()

        if guess in guessed_letters:
            print("You've already guessed that letter!")
        elif guess in word:
            for i, letter in enumerate(word):
                if letter == guess:
                    guessed_word[i] = guess
            print(f"Correct! {' '.join(guessed_word)}")
        else:
            attempts -= 1
            print(f"Wrong! You have {attempts} attempts left.")

        guessed_letters.append(guess)

    if ''.join(guessed_word) == word:
        print(f"Congratulations! You've guessed the word '{word}'!")
    else:
        print(f"Sorry, you've run out of attempts. The word was '{word}'.")

# Start the game
play_game()

Marvin 