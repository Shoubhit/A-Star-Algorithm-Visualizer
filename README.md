# Pathfindertool
This repository contains a Python implementation of the A* pathfinding algorithm using the Pygame library to visualize the algorithm in action. The A* algorithm is used to find the shortest path between two points on a grid while avoiding obstacles.
The A* (pronounced "A-star") algorithm is a widely used pathfinding algorithm in computer science and artificial intelligence. It's used to find the shortest path from a starting point to a target point on a graph, grid, or any network where movement has associated costs. Here's a step-by-step explanation of how the A* algorithm works:

Initialization:
Create an open set, which is a priority queue initially containing only the start node.
Create a closed set (or visited set), initially empty.
Initialize the g-score and f-score for each node. The g-score represents the cost from the start node to the current node, and the f-score is the sum of the g-score and an estimate of the cost from the current node to the target node. Initially, set the g-score to infinity for all nodes except the start node, which has a g-score of 0. Set the f-score to infinity for all nodes.

Main Loop:
While the open set is not empty:
Select the node in the open set with the lowest f-score. This node is the current node.
If the current node is the target node, you have found the shortest path. Stop and reconstruct the path.
Remove the current node from the open set and add it to the closed set to mark it as visited.

Neighbor Expansion:
For each neighbor of the current node:
If the neighbor is already in the closed set, skip it (it has already been explored).
Calculate a tentative g-score for the neighbor. This is the sum of the g-score of the current node and the cost to move from the current node to the neighbor.
If the neighbor is not in the open set or the new g-score is lower than its previous g-score:
Update the neighbor's g-score to the new, lower value.
Calculate the neighbor's f-score by adding its g-score to an estimate of the cost from the neighbor to the target node (heuristic function).
If the neighbor is not in the open set, add it to the open set.

Path Reconstruction (if the target is reached):
Once the target node is reached, you can reconstruct the shortest path by backtracking from the target node to the start node using the came_from dictionary or data structure, which stores the parent node for each node along the path.

Termination:
If the open set becomes empty and the target node is not reached, there is no path from the start node to the target node.
Optimality and Heuristic Function:

A* is guaranteed to find the shortest path if the following conditions are met:
The heuristic function used to estimate the cost from a node to the target node is admissible, meaning it never overestimates the true cost. In other words, the heuristic function should be optimistic.
The graph or grid has no negative edge weights.

## Controls:
Left-click on the grid to set the start and end points. You can only set one start point and one end point.  
Left-click on the grid again to create barriers (obstacles) that the algorithm should navigate around.  
Right-click on the grid to remove barriers or reset the start and end points.  
Press the SPACEBAR to start the A* algorithm. It will find the shortest path from the start to the end while avoiding barriers.  
Press 'C' to clear the grid and start over.

## Visualization:
The visualization uses different colors to represent the various elements on the grid:

White: Empty cells
Orange: Start point
Turquoise: End point
Black: Barriers (obstacles)
Red: Closed nodes (nodes that have been explored)
Green: Open nodes (nodes in the queue for exploration)
Purple: Path found from start to end
