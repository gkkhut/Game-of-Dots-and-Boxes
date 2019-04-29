# Game-of-Dots-and-Boxes

This project is about making use of a Q-learning algorithm to implement a game-playing agent which learns how to play a game of 3x3 Dots and Boxes optimally against an automated player.

### Dots & boxes is a 2-player game.

The starting state is an empty grid of dots (16 dots in case of a 3x3 size board). Both players take turns making a move; a move consists of adding either a horizontal or vertical line between two unjoined adjacent dots. If making a move completes a 1x1 box, then the player who made that move wins that particular box (essentially, gets a point); the player also retains their turn. The game ends when there are no more available moves left to make. The player with the most points number of points is the winner of the game.

Determining how to store and represent the game is a bit tricky, since both the dots and their intermediate edges are valid to the game state. However, representing both dots and edges is not feasible since doing so requires either multiple lists or nested ones, both of which are not unviable to use as input parameters to the neural network.

One can, however, observe that the dots are constant for every state. Hence, a game state can be represented solely by its edges. All edges in the game are represented as a list (of length 24, since there are 24 edges in a 3x3 size game), with 0 denoting that an edge does not exist, and one denoting otherwise.

## Requirements 

* Python 3
* Numpy
* Tensorflow 1.1
* Anaconda

## Instructions

#### To play a game against trained model

* `clone the repository`
* `open a terminal`
* `run dots&boxes_Play.py`

This command brings up a console-based game of dots and boxes where you can play against the trained model on a 3 x 3 board.

You can also elect to be player 2 by using the optional parameter `player-choice`

`python3 dots&boxes_Play.py --player-choice 2`

The edge ordering being considered is:

**&#183;**&nbsp;&nbsp;&nbsp; 0 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp;&nbsp; 1 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp;&nbsp; 2 &nbsp;&nbsp;&nbsp;**&#183;**  
12 &nbsp;&nbsp;&nbsp;&nbsp; 13 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 14 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 15  
**&#183;**&nbsp;&nbsp;&nbsp; 3 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp;&nbsp; 4 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp;&nbsp; 5 &nbsp;&nbsp;&nbsp;**&#183;**  
16 &nbsp;&nbsp;&nbsp;&nbsp; 17 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 18 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 19  
**&#183;**&nbsp;&nbsp;&nbsp; 6 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp;&nbsp; 7 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp;&nbsp; 8 &nbsp;&nbsp;&nbsp;**&#183;**  
20 &nbsp;&nbsp;&nbsp;&nbsp; 21 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 22 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 23  
**&#183;**&nbsp;&nbsp;&nbsp; 9 &nbsp;&nbsp;&nbsp;**&#183;**&nbsp;&nbsp; 10 &nbsp;&nbsp;**&#183;**&nbsp;&nbsp; 11 &nbsp;&nbsp;**&#183;** 

#### To train a model

* `open anaconda navigator` 
* `activate your virtual enironment`
* `open a Jupyter Notebook`
* `Run dots&boxes_train.ipynb`

Currently, this file is hard-coded to halt at 10000 iterations. 
Since the current model has already been trained on 10000 iterations, 
you must either delete the previous model AND log file (located in the models/size3 subdirectory) or 
manual change the iteration limit in the Train_Dots_Boxes.ipynb main program if you wish to run a training simulation. 
This parameter is denoted by `n_games`
