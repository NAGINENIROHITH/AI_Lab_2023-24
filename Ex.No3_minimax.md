# Ex.No: 3  Implementation of Minimax Search
### DATE: 11/03/2025                                                                           
### REGISTER NUMBER : 212222040105
### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

### Program:
```
import math

def minimax(depth, node_index, is_max, values, max_depth):
    if depth == max_depth:
        return values[node_index]
    
    if is_max:
        return max(minimax(depth + 1, node_index * 2, False, values, max_depth),
                   minimax(depth + 1, node_index * 2 + 1, False, values, max_depth))
    else:
        return min(minimax(depth + 1, node_index * 2, True, values, max_depth),
                   minimax(depth + 1, node_index * 2 + 1, True, values, max_depth))

# Example leaf node values
values = [3, 5, 2, 9, 12, 5, 23, 23]
max_depth = math.log2(len(values))

# Find the optimal value for MAX player
optimal_value = minimax(0, 0, True, values, int(max_depth))
print("The optimal value for MAX player is:", optimal_value)

```

### Output:
![image](https://github.com/user-attachments/assets/c042e432-19d3-4ac4-ab73-c1dfb815c3a3)


### Result:
Thus the optimum value of max player was found using minimax search.
