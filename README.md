# 5-in-a-Row vs. AI

**This project is hosted and playable on Firebase:**

**https://ville-angular.web.app/**

This web application project was programmed using Angular framework. I did this during summer 2020. I had no previous experience with Angular and the purpose of this project was to learn the framework and get general practice in programming.

I started with a standard Tic-tac-toe game with a 3x3 board where the player played against an "AI" which simply chose a move at random. Because a 3x3 board for 3-in-a-row against a completely random AI isn't a particularly interesting as a game or as a development challenge, I developed the game and the AI further.

The game is now a 10x10 board where 5-in-a-row wins.

The AI uses a minimax algorithm to determine the plays it makes. To make the game enjoyable I decided that the AI has to make its moves in 250 milliseconds. However, the large board provides a challenge for the AI algorithm because the search space gets massive as the growth is exponential. The current AI uses breadth-first search but because there isn't enough time to get very deep in the search, it relies a lot on the evaluation function being strong enough. The evaluation function recognizes many different types of game states which lead to desirable or undesirable scenarios for the AI and scores them appropriately; trying to win or to stop the player from winning. For example, an open-ended line of 4-in-a-row or the slightly more advanced two open-ended lines of 3-in-a-row always lead to victory.

To help the speed of the search, the algorithm only looks for plays in squares close to ones which already have playmarks in them, as there is little or no reason to play anything in a corner with no other playmarks near. The algorithm also utilizes Alpha-Beta pruning to abandon search paths which are for sure going to be weaker than other already found paths.

All in all, the performance of the AI is satisfactory. It is certainly not an easy opponent.

For future development, multithreading with web workers should be utilized to allow the AI to search deeper. Other types of algorithms, such as depth-first search and Monte Carlo, should also be tested.
