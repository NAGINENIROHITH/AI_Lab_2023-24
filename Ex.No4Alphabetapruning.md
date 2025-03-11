# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE: 11/03/2025                                                                         
### REGISTER NUMBER : 212222040105
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### Steps:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:
```
import math

def alphabeta(depth, node_index, is_max, values, alpha, beta, max_depth):
    if depth == max_depth:
        return values[node_index]
    
    if is_max:
        best = -1000
        for i in range(2):
            val = alphabeta(depth + 1, node_index * 2 + i, False, values, alpha, beta, max_depth)
            best = max(best, val)
            alpha = max(alpha, best)
            if beta <= alpha:
                break
        return best
    else:
        best = 1000
        for i in range(2):
            val = alphabeta(depth + 1, node_index * 2 + i, True, values, alpha, beta, max_depth)
            best = min(best, val)
            beta = min(beta, best)
            if beta <= alpha:
                break
        return best

# Example leaf node values
values = [3, 5, 2, 9, 12, 5, 23, 23]
max_depth = 3

# Find the optimal value for MAX player
optimal_value = alphabeta(0, 0, True, values, -1000, 1000, max_depth)
print("The optimal value for MAX player is:", optimal_value)
```
### Output:
![image](https://github.com/user-attachments/assets/7972a812-3556-45c1-86d1-eb00142f5acf)


### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
