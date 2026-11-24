# CycloneArduino
Cyclone is a popular game found in most arcades. It involves a player timing a button press when an LED light hits a certain location. Normally, in an arcade, a player only has one chance to press the button to land on the correct LED. Otherwise, they immediately lose. In this version of Cyclone however, the game will start off with a set light speed, with a marked light as the target for the player. Every successful timed button press will result in a point earned, and the speed of the light increasing. The goal of the game is to score as many points as possible. The game continues until the player fails to time the button press properly (i.e. the light does not land on the target).

**Hardware Components**
Computing
ATmega328 Microcontroller

**Inputs**
Control button: to stop the light (for the game itself)
Stop button and reset button

**Outputs**
HiLetgo MAX7219 Dot Matrix Module for Arduino Microcontroller 4 in 1 Display with 5pin Line - This is to output the actual game itself, and messages before the game starts.
Passive buzzer - This will play certain notes denoting a successful button press or failed button press. A simple tune will also be played throughout the game.
4D7S - This will be used to output the current score.

**Microcontroller Pins**
PB6, PB5, and PB4 will be used for the MAX7219.
PB3 and PB2 will be used for the 4D7S. The other 2 pins are used for 5V and GND.
PB1 and PB0 will be used for passive buzzers. The other 2 pins are used for 5V and GND. (one to play music, the other for sound effects)
PC5, PC4, and PC3 will be used for the buttons.

**Basic Functionality**

This game will be single player. There will be three total buttons: one to start the game, one to press during the game, and one to end the game. The player must press the start button to begin the game. The LED should display the title of the game in this state: “CYCLONE.”

When the start button is pressed, the game will countdown 5 seconds. A “ping” sound should play every time the countdown timer decrements. The countdown will be displayed on the Dot Matrix Module. 

When the countdown timer hits 0, a more high pitched “ping” will play, signalling the start of the game. The Dot Matrix Module should light up the borders red. A red dot will light up close to one of the border dots signalling the correct dot to stop the player dot on. (In short, around the border there will be red dots, but there will be one section where there is a red dot directly on top of the border. This will be the target.) Another dot will appear and move around the red lighted border at a set interval.

When the player’s red dot and the set red dot overlap and the button is pressed, the passive buzzer should make a “DING” sound, signalling a successful button press. The score is then increased by 1, and a new randomized location for the next dot is lit up.

Every 10 points scored, the speed at which the player’s dot moves should increase.

When the player’s red dot and the set red dot do NOT overlap and the button is pressed, the passive buzzer should make a “BUZZ” sound, signalling a failed button press. The dot matrix module then outputs “GAME OVER,” and tells the player that their final score can be seen on the 4D7S display.

When the game is over and the reset button is pressed, the game should go back to the start state (where it displays the title of the game).
