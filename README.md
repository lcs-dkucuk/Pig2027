#  Pig 
You against another person, using this computer. The objective is to reach a total of 80 points before your opponent. Every available number is equally likely to be rolled.
 
## How to play 
2. **Player 1:** Click **Roll** to roll a virtual six-sided die, and click **Hold** to end the turn and add your total from that turn to your overall total sum. 
If you roll any number except 1, that number will be added to your total for that turn. However, if you roll a 1, your total from this turn will be eliminated and the turn will pass to Player 2.
3. If you roll above 15 during one turn, the die will end up only having the numbers **1-5**. If you go above 25, only **1-4** will be available, and if you go above 35, only the numbers **1-3** will be available to roll. However, you will be granted **one** additional roll without the new debuff after you exceed the required amount.
4. When your turn is over, **Player 2**'s turn will begin, following the same guidelines. The first person to reach a total of 80 points wins.

 
## What I added 
- In the roll after a player rolls the die to achieve a turn total that is over 15 points, 6 is removed from the die, meaning the player can only roll a number from 1 to 5. This means that there is an additional roll without the debuff after the turn total exceeds 15 points.
  - The range of available numbers similarly becomes 1-4 when the turn total exceeds 25 points.
  - Lastly, the range of available numbers similarly becomes 1-3 when a turn total over 35 points is achieved. No other debuffs occur after this one.
  - The button that used to simply state "Roll" now states "Roll from 1-6", "Roll from 1-5", "Roll from 1-4", or "Roll from 1-3" as needed.

 
## Testing
| Test | Chosen input |Should happen |  Did happen |
| --- | --- | --- | --- |
|  Getting a die debuff for 15+ points | Normal die set to 2-6. Roll the die until 15+ points is achieved. | 1-5 die debuff being visibly activated and operational | 1-5 die debuff being visibly activated and operational      
| Getting another die debuff for 25+ points | Normal die and previous debuff set to 2-6 and 2-5. Roll the die until 25+ points is achieved. | 1-4 die debuff being visibly activated and operational | 1-4 die debuff being visibly activated and operational |
| Getting another die debuff for 35+ points (the last programmed debuff) | Normal die and previous debuffs set to 2-6, 2-5, and 2-4. Roll the die until 35+ points is achieved. | 1-3 die debuff being visibly activated and operational | 1-3 die debuff being visibly activated and operational |
| Die resetting after pressing "Hold" and reaching a debuff | Roll until a debuff is activated, then click "Hold" | Current player switching and die resetting to normal (1-6) settings after "Hold" is clicked | Current player switching and die resetting to normal (1-6) settings after "Hold" is clicked |
| Die resetting after reaching a debuff and rolling a 1 | Roll until a debuff is activated, then roll a 1 | Current player switching and die resetting to normal (1-6) settings | Current player switching and die resetting to normal (1-6) settings |
| Die resetting after pressing "New Game" and reaching a debuff | Roll until a debuff is activated, then click "New Game" | Die resetting to normal (1-6) settings after "New Game" is clicked, and all points being reset to 0 | Die resetting to normal (1-6) settings after "New Game" is clicked, and all points being reset to 0 |


## Credits 
- The starting game was written by Mr. Gordon.
- Mr. Gordon also assisted in debugging this program.
- The remainder of this project was created by Deniz Kucuk.
