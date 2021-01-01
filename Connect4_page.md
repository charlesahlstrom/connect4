# Connect 4 AI

In this post, I present the strategy and algorithms I used to build a AI that can play me in the game Connect4.  This is a game that can be completed under a brute-force approach, but as I explain below, there are opportunities to apply algorithsm with optimizing layers to construct a decent AI to play against.  At the time of writing this post, I am building exposure to some AI/machine learning themes, and I thought there is no better way to spend my winter break than building a machine that plays me in one of my favorite bar games.  For those interested in more, please refer to the sources listed below for additional resources I found to be extremely helpful.  

To start, here is a gif of a game from my Python script:

(Placeholder for gif showing game)

## History of Connect4

Connect4 is marketed as a children's boardgame by Milton Bradley created in 1974.  The objective of the game is to take alternating turns and drop tokens into the game's grid slots to achieve a chain of 4 before your opponent can do so.  Two solutions were developed within 15 days of eachother in October 1988 and modern computing power allows for a brute-force solution; however, the number of different trees are numerous and there are applications of algorithms that can be applied to construct a decent AI to play against that can play with a reasonable PAUSE RATE (look up word for when alogirthm is thinking).  


The immediate thought when constructing this AI may be to use a brute-force approach--afterall, Connect 4 heuristically seems like a beefed up version of a tic-tac-toe game. This is a fallacy as the total number of tic-tac-toe board iterations are 255,168 while the number of Connect 4 iterations are calcualted to be 4,531,985,219,092[1](https://oeis.org/A212693).  Traversing this tree under a brute-force approach is not a great solution to this exercise, and we can instead use a collections of algorithms to create a dynamic and semi-decent AI to play against.  


## Minimax Algorithm

The first step when constructing an AI to play connect for is to apply a minimax algorithm.  This is the overarching structure that we can use to define the best move for the computer to choose from.   [pseduocode](https://en.wikipedia.org/wiki/Minimax#Pseudocode)


With this strategy in mind, you can then add on several optimizers and supplemental procedures to improve time performance. 


## Alpha-Beta Pruning Algorithm

The most immediate improvement to the minimax algorithm is to append an alpha-beta pruning algorithm.  The idea behind this procedure is to recgonize that some choices are no where near to being remotely optimal in the AI's choiceset and therefore should be removed from the decision tree.  This pruning

[pseduocode](https://en.wikipedia.org/wiki/Alpha–beta_pruning#Pseudocode)

## Transpoition Table
An added layer of code can be applied in order to include a tarnspoition table.  In a game, there are more than one sequnce of moves to arrive at a specific board's state.  Therefore, we can identify duplicated nodes in the decision tree, and skip over the choice permutations.  




## Converting Pandas Board to a Bit Board
A final piece of optimization is converting these game board from a Pandas arrary into a bit representation.  





# Notes on Strategy

Intuitively, this reduces down to playing moves that build on your current chains of tokens or blocking your opponents chain of tokens.

Additional strategies vary in terms of generality (e.g. playing the middle to maximize chances of diagonal and horizontal wins, playing tokens which force your opponent into playing in a different spot) or more specific (e.g. the "figure 7" which guarentees either a horiztonal or diagonal win, or "odd-even" strategy in which you force your opponent into specific columns in order to win due to a filled board).  All of this is to say that like any good player, the AI will have to think several turns ahead.  






# Reflection
This was an exercise I worked on during my winter break to keep busy and gain exposure into some AI/machine learning techniques/procedures.  In my past research prohjects involving big data, I had a general degree of optimized run-time under the constraints given.  Supplementary tasks to this research did not require highly  optimized script for analying data, and I remember taking some shortcuts to apply some brute-force approaches when time was not an issue. Future work will no doubt require speedy comutations and this exercise has given a deeper appreciation and exposure into finding layers of optimiation to speed up processes. 


# Sources
http://web.mit.edu/sp.268/www/2010/connectFourSlides.pdf
http://blog.gamesolver.org
https://www.youtube.com/watch?v=MMLtza3CZFM
