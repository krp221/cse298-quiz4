# CSE 298 - Quiz 4

Due: 8/04 by end of day

Make at least 1 commit per question.

## Question 1

What is the difference between Dijkstra's Algorithm and A*. Why would one use Dijkstra's over A* and vice versa?
Dijkstra's Algorithm first goes to the path with the lowest cost neighbor and continues to do so until it reaches its final goal node. It will go back to the original node and repeat the process of finding the lowest cost, but with its second lowest cost neighbor to go through each path completely. It goes through every single path until it finds that the cost is the lowest compared to all other paths. A* uses a heuristic function, such as giving priority to nodes with smaller distances as well as calculating the Manhattan distance. One may use Dijkstra's over A* if funds are low, since A* is more expensive to use for computation, or if path is not specific. One may use A* if timing is limited for computation/calculation, or if movement is only lateral. 

## Question 2

Consider the following robot in a grid 2D grid world:

![Gridworld](https://github.com/cmontella/cse298-quiz4/blob/master/gridworld.png?raw=true)

The cell (0,0) is at the bottom left. The robot starts at cell (3,3) and is facing in the 0 radians direction. The robot's goal cell is (12,1), facing the 0 radians direction as well.

Perform the A* algorithm by hand to find the shortest path from the robot's starting location to the goal. Write down each step of the algorithm, including the current cell, open set of cells O, the closed set of cells C, the parent of each cell, and the current g-score and f-scores for each cell (these can be a sparse lists i.e. you don't need to write the scores/parents of the cells haven't been considered by the algorithm yet). You can use any heuristic you like, but specify the one you are using.


## Question 3

List out the cells that represent the shortest path you found above. Then list the commands that would need to be sent to the robot to follow this path. The robot in question moves perfectly without any error, and reponds to two commands: it can either move forward a specified number of cells with `move(cells)`, or it can turn with `turn(radians)`. The robot should end at the goal the same direction at which it faced originally.
