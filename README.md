# Othelo-Game-AI-Project
# Programming Language & Tools:
The project is made with C++ and CLR library for the GUI\
Tools used: Visual Studio 2019\
# Game Playing Supported algorithms:
The main algorithm used for the game playing is MinMax with alpha-beta pruning algorithm.\
The first function used in thinking, is the aiThink() function, it’s purpose is to act as
an entry point for the algorithm, it calulates all the possible moves from a single state, loop over them and call the minMaxAlphaBeta function.\
The main function is minMaxAlphaBeta which is a recursive function implementing the algorithm.\
The minMaxAlphaBeta internally calls the calcHeuristic function which calculates the value of the leave nodes based on some heuristics (discussed below).\
# Heuristics:
1)Mobility:\
It measures how many possible moves in the next state for the player relative
to the opponent, It simply calls a function calcLegalMoves() which returns the
total number of available moves. After calling it twice, for the maximizer and
the minimizer, then the mobility is calculated as follows
mobility = (100 * (maxCount - minCount)) / (maxCount + minCount).\
2)Coin Parity:\
It’s responsible for calculating the total number of coins for both players\
3)Corners Captured:\
It gives higher values for cells at the four corners of the board, since the coins
at the four corners are stable and can’t be flipped, so they should have higher
weight in calculating the heuristics\
