from pysinewave import SineWave
from time import sleep
from random import randrange

def diffi(difficulty):
    if difficulty == '1':
        pitcheasy(difficulty)
    elif difficulty == '2':
        pitchhard(difficulty)

def pitcheasy(difficulty):
    a = randrange(0, 11)
    randpitch = pitches1[a]
    #print(randpitch)

    # Setting "a" to be the correct number to play the corresponding pitch found in the "pitches1" list
    sine = SineWave(pitch=a)

    print(f'For accidentals: "#" for sharp, do not use regular flats')

    play(sine, randpitch, difficulty)

def pitchhard(difficulty):
    a = randrange(0, 22)
    randpitch = pitches2[a]
    #print(randpitch)

    # Setting "a" to be the correct number to play the corresponding pitch found in the "pitches2" list
    a /= 2
    sine = SineWave(pitch=a)

    print(f'For accidentals: use "/" for half sharp, "#" for sharp, "d" for half flat, do not use regular flats')

    play(sine, randpitch, difficulty)

def play(sine, randpitch, difficulty):
    # Playing the pitch
    print('Playing pitch')
    sine.play()
    sleep(5)
    sine.stop()

    guess(randpitch, difficulty)

def guess(randpitch, difficulty):
    global score
    guess = input('What was that pitch? ')
    print()
    if guess.lower() == 'stop':
        print('Thank you for playing!')
    elif guess.lower() == randpitch:
        print(f'You win!! The correct pitch was {randpitch}')
        score += 1 * int(difficulty)
        print(f'Your current score is {score}')
        diffi(difficulty)
    else:
        print(f'Sorry! The correct pitch was {randpitch}')
        score = 0
        print(f'Your current score is {score}')
        diffi(difficulty)

if __name__ == '__main__':
    pitches1 = ['c', 'c#', 'd', 'd#', 'e', 'f', 'f#', 'g', 'g#', 'a', 'a#', 'b']
    pitches2 = ['c', 'c/', 'c#', 'dd', 'd', 'd/', 'd#', 'ed', 'e', 'e/', 'f', 'f/', 'f#', 'gd', 'g', 'g/', 'g#', 'ad',
                'a', 'a/', 'a#', 'bd', 'b']
    score = 0
    print()
    print()
    print('Enter "stop" whenever you would like to stop playing')
    difficulty = input(f'Welcome to the pitch guessing game! Enter a "1" for easy and a "2" for hard: ')
    diffi(difficulty)
