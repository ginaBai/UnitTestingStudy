# Project Instructions - BSK

The objective is to implement an application that can calculate the score of a single bowling game. You will be writing code and using existing tests to determine if your code meets the specification.

**Bowling Game Description**

A bowling game consists of 10 frames as shown below. In each frame the player has two opportunities to knock down 10 pins. The score for the frame is the total number of pins knocked down, plus bonuses for strikes and spares.

![ExampleImage]()

A spare is when the player knocks down all 10 pins in two throws. The bonus for that frame is the number of pins knocked down by the next throw. So in frame 3 of the example game below, the score is 10 (the total number knocked down) plus a bonus of 5 (the number of pins knocked down on the next throw).

A strike is when the player knocks down all 10 pins on his first try. The bonus for that frame is the value of the next two throws. 

In the tenth frame, a player who rolls a spare or strike is allowed to have bonus throws to complete the frame. However, no more than three balls can be rolled in tenth frame.

## Task Requirement 
The application’s requirements are divided into a set of user stories, which serve as your to-do list. You should be able to incrementally develop a complete solution without an upfront comprehension of all the game’s rules. Don’t read ahead, and handle the requirements one at a time in the order provided.

Only when a story is done, move on to the next one. A story is done when you are confident your program correctly implements all the functionality stipulated by the story’s requirement. This implies ALL of your test cases for that story and ALL of the test cases for the previous stories pass. You may need to tweak your solution as you progress towards more advanced requirements.

**Supportive Links**  

[YouTube Video for Detailed Rules and Examples of Scoring a Game of Bowling](https://www.youtube.com/watch?v=aBe71sD8o8c)

[Online Bowling Game Score Calculator](https://bowlinggenius.com)

## 1: Frame
*Each turn of a bowling game is called a **frame**. 10 pins are arranged in each frame. The goal of the player is to knock down as many pins as possible in each frame. The player has two chances, or **throws**, to do so. The value of a throw is given by the number of pins knocked down in that throw.*

**Requirement:** Define a frame as composed of two throws. The first and second throws should be distinguishable.

**Example:** [2, 4] is a frame with two throws, in which two pins were knocked down in the first throw and four pins were knocked down in the second.

## 2: Frame Score
*An ordinary frame’s score is the **sum** of its throws.*

**Requirement:** Compute the score of an ordinary frame.

**Examples:** The score of the frame [2, 6] is 8. The score of the frame [0, 9] is 9.

## 3: Game
*A single game consists of **10** frames.*

**Requirement:** Define a game, which consists of 10 frames.

**Example:** The sequence of frames [1, 5] [3, 6] [7, 2] [3, 6] [4, 4] [5, 3] [3, 3] [4, 5] [8, 1] [2, 6] represents a game. You will reuse this game from now on to represent different scenarios, modifying only a few frames each time.

## 4: Game Score
*The score of a bowling game is the **sum** of the individual scores of its frames.*

**Requirement:** Compute the score of a game.

**Example:** The score of the game [1, 5] [3, 6] [7, 2] [3, 6] [4, 4] [5, 3] [3, 3] [4, 5] [8, 1] [2, 6] is 81.

## 5: Strike
*A frame is called a **strike** if all 10 pins are knocked down in the **first throw**. In this case, there is no second throw. A strike frame can be written as [10, 0]. The score of a strike equals 10 **plus** the sum of the **next two** throws.*

**Requirement:** Recognize a strike frame. Compute the score of a strike. Compute the score of a game containing a strike.

**Examples:** Suppose [10, 0] and [3, 6] are consecutive frames. Then the first frame is a strike and its score equals 10 + 3 + 6 = 19. The game [10, 0] [3, 6] [7, 2] [3, 6] [4, 4] [5, 3] [3, 3] [4, 5] [8, 1] [2, 6] has a score of 94.

## 6: Spare
*A frame is called a **spare** when all 10 pins are knocked down in **two throws**. The score of a spare frame is 10 **plus** the value of the first throw from the **subsequent** frame.*

**Requirement:** Recognize a spare frame. Compute the score of a spare. Compute the score of a game containing a spare frame.

**Examples:** [1, 9], [4, 6], [7, 3] are all spares. If you have two frames [1, 9] and [3, 6] in a row, the spare frame’s score is 10 + 3 = 13. The game [1, 9] [3, 6] [7, 2] [3, 6] [4, 4] [5, 3] [3, 3] [4, 5] [8, 1] [2, 6] has a score of 88 (13 + 9 + 9 + 9 + 8 + 8 + 6 + 9 + 9 + 8).

## 7: Strike and Spare
*A strike can be followed by a spare. The strike’s score is not affected when this happens.*

**Requirement:** Compute the score of a strike when it’s followed by a spare. Compute the score of a game with a spare following a strike.

**Examples:** In the sequence [10, 0] [4, 6] [7, 2], a strike is followed by a spare. In this case, the score of the strike is 10 + 4 + 6 = 20, and the score of the spare is 4 + 6 + 7 = 17. The game [10, 0] [4, 6] [7, 2] [3, 6] [4, 4] [5, 3] [3, 3] [4, 5] [8, 1] [2, 6] has a score of 103.


## Congratulations, you are done! Thanks again for participating in this study!
