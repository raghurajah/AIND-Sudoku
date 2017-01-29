# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked Twins become yet another base strategy to reduce the search space,
before actually performing the search. In my implementation, I have applied
the naked_twins call along with the eliminate and only_choice strategy calls.
This reduces the search space and then this is sent into the recursive DFS
to traverse the tree. The implementation of the strategy is pretty straightforward.
We walk through each unit and identify boxes that are twins (two digit values, that
are the same). Once the twins are identified, we traverse the unit and remove
the twin values from the peers within this unit.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Diagonal sudoku are additional constraints imposed on possible values
for a box. There are two diagonal units - forward and backward. We simply add
these units into the unitlist, so when the peers are calculated, this is considered
and added as peers to box that intersect with the diagonal unit. The boxes that
intersect with the diagonals (except the middle one - E5), now have 26 peers
instead of 20. The middle one E5 has 32 peers. Naturally, not all normal sudoku will
have solutions with diagonal constraints, only a subset will.   

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project.
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
