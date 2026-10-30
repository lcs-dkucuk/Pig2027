#  Pig 
You against another person, using this computer. The objective is to reach a total of 80 points before your opponent. Every available number is equally likely to be rolled.
 
## How to play 
1. **Player 1:** Click **Roll** to roll a virtual six-sided die, and click **Hold** to end the turn and add your total from that turn to your overall total sum. 
If you roll any number except **1**, that number will be added to your total for that turn. However, if you roll a **1**, your total from this turn will be eliminated and the turn will pass to **Player 2**.
2. If you roll above 15 during one turn, the die will end up only having the numbers **1-5** for your next rolls. If you go above 25, only **1-4** will be available, and if you go above 35, only the numbers **1-3** will be available to roll.
3. When your turn is over, **Player 2**'s turn will begin, following the same guidelines. The first person to reach a total of **80 points** wins.

## How it works: The probability warning message
- The probability shown in the warning message is the difference in probability between rolling a 1 with the current die and rolling a 1 on the normal die. This is calculated in the same function as the one that determines the "type" of debuff (die being from 1-5, 1-4, or 1-3). This function is called immediately after the current roll is added to the total for that turn, meaning it is continously up to date. 
- The probability is calculated using doubles (non-integers). For example, the calculated probability for the 1-4 debuff is 1/4 - 1/6. This value is multiplied by 100 within the function, so it can be presented as a percentage in the message. Then, the number of digits after the decimal point that will be displayed (two in my game) is determined in the constant formattedProbability. 
- Thus, the string (stored in probabilityMessage) is created using formattedProbability and programmed into the UI using the template for the string "message".
- When the die is normal (can roll from 1 to 6), probabilityMessage is assigned " ", which is an empty string and is not visible in the game. probabilityMessage is also assigned this value when the current player switches, the player holds, and when a new game is begun.
 
 
## What I added 
- In the roll after a player rolls the die to achieve a turn total that is over 15 points, 6 is removed from the die, meaning the player can only roll a number from 1 to 5.
  - Also, the range of available numbers similarly becomes 1-4 when the turn total exceeds 25 points.
  - Lastly, the range of available numbers similarly becomes 1-3 when a turn total over 35 points is achieved. No other debuffs occur after this one.
- The button that used to simply state "Roll" now states "Roll from 1-6", "Roll from 1-5", "Roll from 1-4", or "Roll from 1-3" as needed.
- When a debuff is activated, a message appears, warning the player of the increased probability (percentage) of rolling a 1 compared to the normal die.

 
## Testing
| Test | Chosen input |Should happen |  Did happen |
| --- | --- | --- | --- |
|  Getting a die debuff for 15 points | Normal die set to 5. Roll the die until 15 points is achieved. | 1-5 die debuff being visibly activated and operational, and appropriate warning message being shown | 1-5 die debuff being visibly activated and operational, and appropriate warning message being shown       
| Getting another die debuff for 25 points | Normal die and previous debuff set to 5. Roll the die until 25 points is achieved. | 1-4 die debuff being visibly activated and operational, and appropriate warning message being shown | 1-4 die debuff being visibly activated and operational, and appropriate warning message being shown |
| Getting another die debuff for 35 points (the last programmed debuff) | Normal die and previous debuffs set to 5. Roll the die until 35 points is achieved. | 1-3 die debuff being visibly activated and operational, and appropriate warning message being shown | 1-3 die debuff being visibly activated and operational, and appropriate warning message being shown |
| Die resetting after pressing "Hold" and reaching a debuff | Normal die and all debuffs set to 5. Roll until a debuff is activated, then click "Hold" | Current player switching and die resetting to normal (1-6) settings after "Hold" is clicked, and warning message disappearing | Current player switching and die resetting to normal (1-6) settings after "Hold" is clicked, and warning message disappearing |
| Die resetting after reaching a debuff and rolling a 1 | Roll until a debuff is activated, then roll a 1 | Current player switching and die resetting to normal (1-6) settings, and warning message disappearing | Current player switching and die resetting to normal (1-6) settings, and warning message disappearing |
| Die resetting after pressing "New Game" and reaching a debuff | Normal die and all debuffs set to 5. Roll until a debuff is activated, then click "New Game" | Die resetting to normal (1-6) settings after "New Game" is clicked, all points being reset to 0, and warning message disappearing | Die resetting to normal (1-6) settings after "New Game" is clicked, all points being reset to 0, and warning message disappearing |


## Credits 
- The starting game was written by Mr. Gordon.
- Mr. Gordon also assisted in debugging this program.
- The remainder of this project was created by Deniz Kucuk.
