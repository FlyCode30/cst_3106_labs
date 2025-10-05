# Design System Documentation for Michael Kubisewsky's Yahtzee Game

## 1. Overall game logic, rules and primary varaibles used for code

Yatzy is a game in which players roll 5 dice in order to get certain combinations of numbers and accumlate the highest possible score based on those combinations. After the 1st and 2nd roll, players may decide to keep their dice till the end of the turn or roll them again.
In order to create the require code for this game, a modular approach was used to organize the code. This documentation will go over those modules used and an overflow of the game flow that the code creates.
There are 4 main modules used.
- Game logic is the main module used to control the actual game state and DOM elements the player interacts with
- Roll logic are the functions used to roll the dice.
- Score logic determines how scoring is done
- Utility logic, called handle here, contains utility functions that does not fall under any 1 specific function

### General Scoring Rules

Divided into top and bottom scores. A player can only put in 1 score per turn and cannot change the score once it has been put in.

Top Scores: Counts how many times a certain number appears. So there are 6 spots and only that number is counted. So 3 4's would be 12 in the 4 spot.

Bottom Scores: Based on rolled combinations

3 of a kind
4
...

### Primary Variables used

- A roll array that contains the values the player has rolled
- A held array which determines which dice the player wants to keep. 
- A roll count that determines how many times the player has rolled
- Temporary scores. This represents temporary scores the player has at any given time. These scores do no carry on past 1 roll. This is used to help display possible scores the player can choose from at the end of a turn.
Committed scores. These scores represent the scores a player keeps after the end of a turn. These are the ones used to determine total scores
Array counter: This is an array that determines how many of each number a player has. So 1, 1, 3, 4, 6 would be 2, 0, 1, 1, 0, 1. This is used to calculate scores for the combinations.


## 1. Game flow

This well go over the flow of a standard turn for 1 player. Each turn consists of 3 roles, after which a player must put in a score and then roll again.

1. An array of numbers are rolled
2. These numbers are transferred to roll array.
3. Images are rendered based on this rolled array.
4. Array counter is calculated.
5. Choose. Players can choose which dice they want by clicking on a dice. This action changes the status of the held array and will "move" the dice the player wants to keep to a different section. There is no actual change in the rolled array, it only chooses what the player sees.
6. Player can now reroll the dice up to 3 times. Held dice are not rolled again. Including the initial roll, this can be done up to 3 times.
7. Scoring portion
8. All remaining dice are changed to held status and images are rendered
9. Temporary scores (scores for this current round) are calculated
10. Placeholders are shown on the score sheet so players can see their options
11. A player puts in a score they want to keep.
12. The player clicks score.
13. The value put in by the player is converted to a committed score array. These persist over the course of a whole game and are used to calculate totals.
14. Total scores are caculated
15. Totals are filled in on the score sheet
16. Game status is reset. This means resetting the roll count to 0 and changing all held statuses to false.
17. A new roll is carried out and the turn repeats. 


## 2. Game Logic

### Functions

- imports
- load functions
- Variables
- update function
- click functions. Determines what happens on click.
- render functions. Controls the rendering of the DOM elements related to the dice
- controls what happens on each type of roll
- hold functions. Determines what happens when a player clicks a dice to hold it 
- DOM functions. Controls how scoring sheet is filled based on what the player has rolled
- Score functions. Controls scoring for both temporary and committed scores.
- formatting functions. Controls formatting and UI appearance.


## 3. Roll Logic

### functions

getDiceNumber: the function that actually generates the numbers for the rolled arrays. 
rollFullPure: generates an array of numbers using getDiceNumber.
reRollPure: 

## 4. Score Logic

### functions

all scorign is based on the array counter

calcualteTop:
caculateObjectTotal: used to calculate the sum of an object. For this particular game, the object is an array that holds the total scores.
sumFromCounter: used to calculate total value from array counter. Used for chance and kinds.
calculateMaxCount: used to assist in determing kinds and straights
calculateFH: 
....

## 5. Handle Logic (Utility logic)

### functions

getArrayCounterPure: used to get the array counter. Although the array counter is used in scoring, it doesn't actually score anything in of itself. This is why it was put in with the utility functions.










