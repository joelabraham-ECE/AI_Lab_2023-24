# Ex.No: 6   Logic Programming – Factorial of number   
### DATE: 20/09.25                                                                           
### REGISTER NUMBER : 212222060097
### AIM: 
To  write  a logic program  to solve Towers of Hanoi problem  using SWI-PROLOG. 
### Algorithm:
1. Start the program
2.  Write a rules for finding solution of Towers of Hanoi in SWI-PROLOG.
3.  a )	If only one disk  => Move disk from X to Y.
4.  b)	If Number of disk greater than 0 then
5.        i)	Move  N-1 disks from X to Z.
6.        ii)	Move  Nth disk from X to Y
7.        iii)	Move  N-1 disks from Y to X.
8. Run the program  to find answer of  query.

### Program:
```
# Initial values of Alpha and Beta
MAX, MIN = 1000, -1000
# Returns optimal value for current player
#(Initially called for root and maximizer)
def minimax(depth, nodeIndex, maximizingPlayer,values, alpha, beta):
# Terminating condition. i.e
# leaf node is reached
    if depth == 3:
       return values[nodeIndex]
   
    if maximizingPlayer:
        best = MIN
        # Recur for left and right children
        for i in range(0, 2):
          val = minimax(depth + 1, nodeIndex * 2 + i,False, values,alpha, beta)
          best = max(best, val)
          alpha = max(alpha, best)
          # Alpha Beta Pruning
          if beta <= alpha:
             break
        return best
    else:
        best = MAX
        # Recur for left and
        # right children
        for i in range(0, 2):
            val = minimax(depth + 1, nodeIndex * 2 + i,True, values, alpha,beta)
            best = min(best, val)
            beta = min(beta, best)
            # Alpha Beta Pruning
            if beta <= alpha:
               break
        return best
values = [3, 5, 6, 9, 1, 2, 0, -1]
print("The optimal value is :", minimax(0, 0, True, values, MIN, MAX))
```


### Output:
<img width="483" alt="image" src="https://github.com/Vineesha29031970/AI_Lab_2023-24/assets/133136880/a8999b67-6d6a-4d5a-ae56-40ca477560e8">
### Result:
Thus the solution of Towers of Hanoi problem was found by logic programming.
