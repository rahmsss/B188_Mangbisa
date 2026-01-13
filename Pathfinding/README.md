<h1> Pathfinding Algorithm: Lab Activity</h1>

<h2>Part 1: Theoretical Background and Manual Calculation</h2>

The algorithm is an informed search technique that finds the shortest path by calculating a
total estimated cost, F(n), for every node

<h3>The Core Cost Function</h3>
The function is composed of the known cost and the estimated cost:
F(n) = G(n) + H(n)

● G(n) (Cost-to-Start): The actual, confirmed distance traveled from the starting node (S)
to the current node ($n$). On this grid, $G$ increases by 1 for every adjacent step.
● H(n) (Heuristic Cost): The estimated distance from the current node ($n$) to the goal
node (G). We use the Manhattan Distance:

H(n) = |x_n - x_G| + [cite_start]|y_n - y_G|

● F(n) (Total Estimated Cost): The sum, used to prioritize which node to explore next (A*
always chooses the node with the lowest F)

Lab Grid Setup
Use the 5x5 grid below for manual calculations.

X/Y 0 1 2 3 4
0 S       O
1
2    O
3    O O
4           G

●  S: Start (0, 0)
●  G: Goal (4, 4)
●  O: Obstacle (Blocked) 

Procedure: Manual Step-by-Step Calculation 
Step 0: Initialize the Start Node 

●  G(S) = 0 ●  H(S) = |4 - 0| + |4 - 0| = 8 
●  F(S) = 0 + 8 = 8 ●  Open List: [S(0, 0)] 

Step 1: Evaluate S (0, 0)
  1.  Move S to the Closed List.
  2.  Examine neighbors (1, 0) and (0, 1). 

  Neighbor Node   G(n)    H(n) (to (4, 4))         F(n) = G+H  Parent Node 
  (1, 0)           0 + 1 = 1  3 + 4 = 7                8         (0, 0) 
  
  (0, 1)           0 + 1 = 1 4 + 3 = 7                 8         (0, 0)

  3. Open List now contains: (1, 0) and (0, 1).

Step 2: Choose the Next Node 
  1.  Both nodes have F=8. We use the tie-breaker rule: choose the node with the lowest H cost (or lowest G cost, or simply the one first in the list). In this example, they are all tied. We choose (1, 0).
  2.  Move (1, 0) to the Closed List.

Step 3: Evaluate (1, 0)
  1. Examine the valid new neighbor: (2, 0).
  2. (0, 0) is closed; (1, 1) is an obstacle.

Neighbor Node      G(n)      H(n) (to (4, 4))   F(n) = G+H   Parent Node
    (2, 0)      1 + 1 = 2       2 + 4 = 6           8           (1, 0)

  3. Open List now contains: (0, 1) and (2, 0).
   
Step 4: Choose the Next Node (Final Calculation)
  1. Calculate F cost for all nodes currently in the Open List:

 Node   G(n) H(n) F(n)
(0, 1)   1    7    8
(2, 0)   2    6    8

 2. Using the tie-breaker of choosing the lowest H cost, the next node A* selects is (2, 0).

    
