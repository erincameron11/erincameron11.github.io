---
title: 'Hangman - Console Game - Java'
date: 2024-04-26
permalink: /posts/2024/04/hangman-game/
tags:
  - Java
  - Eclipse IDE

---

A Java program for a user to play a simplistic game of Hangman in the IDE console.

## Introduction
The aim of this project is to use Java to design a console-based Hangman Game.    

_Rules of the Game:_
* Objective: Guess the secret word before the stick figure is fully drawn.
* Setup: 
    * The user has 7 `strikes` to guess letters in the word - coinciding to the number of body parts in the stick figure: head, neck, left arm, right arm, torso, left leg, and right leg
    * The stick figure starts without any body parts drawn
* Gameplay:
    * Each turn, the user gets to guess 1 letter. 
        * If the user guesses correctly, `strikes` remains the same, the stick figure does not further progress, and the letter appears on the word display area (eg; guessing `'A'`: `_ _ _ A _`)
        * If the user guesses incorrectly, a body part is added to the stick person, and `strikes` increases by 1. The word display area does not change.
    * If the user reaches 7 strikes, the game ends - LOSER
    * If the user guesses the entire word, the game ends - WINNER    


## Gameplay Sequence
Below we will play a mock-game. First, we see the Hangman start output:
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-start.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />


Then, we guess 3 letters that are incorrect.   
Strike 1:   
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike1.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   

Strike 2:     
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike2.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   

Strike 3:   
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike3.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   
 


But now, we guess correctly!   
Guessing `'A'`:    
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-correct1.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   

Guessing `'M'`:    
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-correct2.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   


But unfortunately, we guess 4 more times, and strike out:   
Guessing `'N'`:     
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike4.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   

Guessing `'W'`:     
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike5.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   

Guessing `'F'`:    
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike6.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   

Guessing `'Y'`:     
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-strike7.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   


But... In another game, we won! Take a look at the winning sequence:     
<img src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/hangman-win.png" style="box-shadow: 10px 10px 5px -4px rgba(0,0,0,0.75);" />   



## Tools & Techniques
* Java
* Eclipse IDE


## Implementation
An `initialize()` method controls the game setup at the beginning of each game. Inside this method, the `hangman` is initialized, the words are read in from the `words.txt` file, a random `word` is selected, for the game, an `answer` key array is created, and a `wordChars` array is created (to identify which letters have been successfully guessed so far).   

The `setHangman(int strikes)` method sets the correct output of the hangman display, based on the number of strikes the user has.   

The `setWordSpaces(char guess)` method controls the actions after a user places a guess. Inside this method, the `wordChars` array is updated to `!` for any correctly guessed values, the `strikes` are increased if the user does not guess correctly, and if all values of the `wordChars` array are exclamation points, the `win` flag is set to `true` to signify that the user has won. The `prompt` message is updated and the `setHangman(int strikes)` is called to update the hangman output.

The `displayWord()` method displays the word prompt area to the user in the console. Inside this method, the `wordChars` exclamation mark values are used to determine what letters to output in the word display area. For example, if `wordChars` is `['J', '!', 'V', '!']`, and the `answer` array is `['J', 'A', 'V', 'A']`, this method would know to print the `A`'s in the word prompt area and ` _ ` for the rest of the un-guessed letters.


Java Classes utilized:
* java.io.BufferedReader --> For reading text in a buffered manner from a character-input stream
* java.io.FileReader --> To read the file
* java.util.ArrayList --> To hold the file words, and letters guessed by the user
* java.util.Scanner --> To accept console input from the user


## Run
To execute the program, follow the instructions below:
1. Clone the git repo: `https://github.com/erincameron11/hangman`
2. Open up the files as a Java project in the IDE of your choice.
3. Run the `HangmanBoard.java` file and follow the commands in the console to play.