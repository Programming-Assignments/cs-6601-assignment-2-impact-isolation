Download Link: https://assignmentchef.com/product/cs-6601-assignment-2-impact-isolation
<br>
<div>
<div># Welcome to Assignment 2 - Impact Isolation!</div>
<div>Your task is to create an AI that can play and win a game of Impact Isolation. Your AI will be tested against several pre-baked AIs as well as your peers’ AI systems. You will implement your AI in Python 3.7, using our provided code as a starting point.</div>
<div>In case we haven't got this into your heads enough: **start early!!!** It is entirely possible, and probably likely, that a large part of your next 2 weeks will be devoted to this assignment, but we hope that it is worth it and you will really enjoy the assignment!</div>
<div>Good luck!</div>
</div>
<div></div>
The rules of Impact Isolation are a variation of the original Isolation game. In the original form of the game there are two players, each with their own game piece, and a 7-by-7 grid of squares. At the beginning of the game, the first player places their piece on any square. The second player follows suit, and places their piece on any one of the available squares. From that point on, the players alternate turns moving their piece like a queen in chess (any number of open squares vertically, horizontally, or diagonally). When the piece is moved, the square that was previously occupied is blocked, and cannot be used for the remainder of the game. The first player who is unable to move their queen loses.

In this variant called Impact Isolation, each player's piece creats an impact crater around itself when it moves **more than one block** in any direction. This impact crater blocks 4 locations (North, South, East, West) around the location the queen moves to, effectively reducing the queen's mobility to that of a bishop the next turn. We start with a 9-by-9 grid in this variation. Neither players can move on or through squares blocked by this impact. For clarity, examine the scenario below:

Q1 places their queen on the board, and Q2 follows suit.
<div><img class="alignnone size-medium wp-image-22351" src="https://assignmentchef.com/wp-content/uploads/2023/02/impact_1-300x300.png" alt="" width="300" height="300" /></div>
Q1 moves horizontally to the right for 4 blocks and creates an impact around it, consequently blocking some of Q2's potential future moves. The previous location of Q1 is also blocked along with the "_impact_"ed locations
<div><img class="alignnone size-medium wp-image-22352" src="https://assignmentchef.com/wp-content/uploads/2023/02/impact_2-300x300.png" alt="" width="300" height="300" /></div>
Q2 makes a single unit block thus not creating any impact but simply blocking the previously held location.
<div><img class="alignnone size-medium wp-image-22353" src="https://assignmentchef.com/wp-content/uploads/2023/02/impact_3-300x300.png" alt="" width="300" height="300" /></div>
Q1 moves diagonally southwest.

.<img class="alignnone size-medium wp-image-22354" src="https://assignmentchef.com/wp-content/uploads/2023/02/impact_4-297x300.png" alt="" width="297" height="300" />

&nbsp;

The game will continue in a similar fashion until either of the queens has no cells left to move
<div>
<div># Important Files</div>
<div>While you'll only have to edit `notebook.ipynb` and submit the exported `submission.py`, there are a number of notable files:</div>
<div>1. `isolation.py`: Includes the `Board` class and a function for printing out a game as text. Do **NOT** change contents of this file. We have the same file on the server's side, so any changes will not be accounted for.</div>
<div>2. `notebook.ipynb`: Where you'll implement the required methods for your agents.</div>
<div>3. `player_submission_tests.py`: Sample tests to validate your agents locally.</div>
<div>4. `test_players.py`: Contains 2 player types for you to test agents locally:</div>
<div>    - `RandomPlayer` - chooses a legal move randomly from among the available legal moves</div>
<div>    - `HumanPlayer` - allows *YOU* to play against the AI in terminal (else use `InteractiveGame` in jupyter)</div>
<div>Additionally, we've included a number of local unit tests to help you test your player and evaluation function as well as to give you an idea of how the classes are used. Feel free to play around with them and add more.</div>
</div>
<div></div>
<div>
<div>
<div># The Assignment</div>
<div>In this assignment you will need to implement evaluation functions and game playing methods. Your goal is to implement the following parts of the notebook:</div>
<div>1. Evaluation functions (`OpenMoveEvalFn` and `CustomEvalFn` if you wish to use the latter)</div>
<div>2. The minimax algorithm (`minimax`)</div>
<div>3. Alpha-beta pruning (`alphabeta`)</div>
<div>4. Adjust the `move()` according to section you are trying to work on.</div>
</div>
<div>
<div>
<div>### Evaluation Functions</div>
<div>These functions will inform the value judgements your AI will make when choosing moves. There are 2 classes:</div>
<div>- `OpenMoveEvalFn` - Returns the number of available moves open for your player minus the number of moves available for opponent player. All baseline tests will use this function. **This is mandatory**</div>
<div>- `CustomEvalFn` - You are encouraged to create your own evaluation function here.</div>
<div>#### Notes on these classes</div>
<div>1. You may write additional code within each class. However, we will only be invoking the `score()` function. You may not change the signature of this function.</div>
<div>2. When writing additional code please try not to copy the existing cells since they contain `#export` comments that is used for converting the notebook to `submission.py` file.</div>
</div>
<div>
<div>
<div>### CustomPlayer</div>
<div>This is the meat of the assignment. A few notes about the class:</div>
<div>- You are permitted to change the default values within the function signatures provided. In fact, when you have your custom evaluation function, you are encouraged to change the default values for `__init__` to use the new eval function.</div>
<div>- You are free change the contents of each of the provided methods. When you are ready with `alphabeta()`, for example, you should update `move()` to use that function instead.</div>
<div>- You are free to add more methods to the class.</div>
<div>- You may not create additional external functions and classes that are referenced from within this class.</div>
<div>Your agent will have a limited amount of time to act each turn (1 second). We will call these functions directly so **don’t modify** the function names and their parameter order.</div>
</div>
<div>
<div>
<div>We have divided the tests into three sections (mentioned in details in next grading section below), each with their own submission limit.</div>
<div>These are the bare minimum requirements for your AI, and the rest is up to you. You will be scored according to how well your AI performs against some baseline AIs that we provide (see [Grading](#Submissions-&amp;-Grading)). If you want to improve over the base performance, here are a few suggestions:</div>
<div>- Use partition techniques.</div>
<div>- Store the evaluation scores for past moves.</div>
<div>- Modify your evaluation function to account for “killer moves”.</div>
<div>- Optimize functions that are called often.</div>
<div>- Order nodes to maximize pruning.</div>
</div>
<div></div>
</div>
</div>
</div>
</div>