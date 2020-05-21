import random
import string
import time


def intro():
    answer_game = input("Would you like to play a game?")
    if answer_game.lower() == ("yes") or answer_game.lower() == ("yeh") or answer_game.lower() == ("yep"):
        print ("Amazing, let's play then!")
    user_name = input("Please, type your name!")
    return (user_name)


def randomString(stringLength=4):
    letters = string.ascii_lowercase
    return ''.join(random.choice(letters) for i in range(stringLength))


def get_user_guess(user_name):
    user_guess = input(user_name + ", please type your guess?")
    return user_guess


def did_user_win(user_guess, computer_guess):
    if computer_guess == user_guess:
        return True
    if computer_guess != user_guess:
        return False


def announcing(user_name, result):
    # result is True if user won
    if result is True:
        print(user_name + ", amazing, you guessed it right!")
    else:
        print(user_name + ", you didnt guess it right!")


def play_again(user_name):
    #question_playagain - bool
    bye_question = input(user_name + ", would you like to play it again?")
    if bye_question.lower() in ["yes", "yeah"]:
        return True
    else:
        return False

user_name = intro()
computer_guess = randomString()
print (computer_guess)

while True:
    user_guess = get_user_guess(user_name)
    winner = did_user_win (user_guess, computer_guess)
    announcing(user_name, winner)
    answer_play_again = play_again(user_name)
    if answer_play_again == False:
        break

