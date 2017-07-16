# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked twin approach is used to reduce the number of possible solutions and, thus, simplify the problem. This is accomplished by looking for pairs of boxes that are located within the same unit(s) and have two and only two identical possible values A and B. While we don't know which value will end up in which box, we can be sure that both of them will be present in this pair of boxes, and as a consequence, cannot be present in any of the other boxes within the same unit(s). We can now use constraint propagation to loop over other boxes within the same unit(s) and remove both A and B from the list of possible values for each of those boxes.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Diagonal sudoku problem imposes additional constraints on the possible values of the boxes compared to "normal" sudoku - it requires each digit to occur once and only once in each of the two main diagonals. This means that each of the main diagonals forms a "unit". And all the digits within the same diagonal become "peers". As a result, we can use our existing code to solve the diagonal sudoku problem by modifying the definition of "unit" and "peer" to incorporate those additional constraints. Practically it means that  the definition of the "peer" (which previously included only boxes within the same row, column, or 3x3 square) now includes all boxes within the same main diagonal.

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

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

