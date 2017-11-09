# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A:  (a) In the first step we identify all the potential pairs of boxes from the grid that are in the same unit and have the same value which is of length "2"
    (b) Next loop over all the pairs and find the lists of units that share in common
    (c) Loop over the boxes in each of the unit lists (except the pair boxes) and replace the digits (value contained in the pair boxes) with space

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A:  (a) Generate lists containing the keys for the two diagonals and add it to the unit list - boxes in diagonals will have 20+6 = 26 peer boxes except E% that will have 20+6+6 = 32 peer boxes
    (b) Call the search function that in turn will call the reduce_puzzle function that wil successively apply the "eliminate" and "choice_only" constraint functions
    (c) Next, if the grid is not solved, identify the box with the least number of possibilities and branch into each of those possibilities and calling the constraint
        propagation functions as you branch
    (d) The search goes from top-down and left to right until the grid is solved or an impasse is reached

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the `assign_value` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login) for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

