# CSE 298 - Quiz 4

Due: 8/04 by end of day

Make at least 1 commit per question.

## Question 1

What is the difference between Dijkstra's Algorithm and A*. Why would one use Dijkstra's over A* and vice versa?

## Question 2

Consider the following robot in a grid 2D grid world:

![Gridworld](https://github.com/cmontella/cse298-quiz4/blob/master/gridworld.png?raw=true)

The cell (0,0) is at the bottom left. The robot starts at cell (3,3) and is facing in the 0 radians direction. The robot's goal cell is (12,1), facing the 0 radians direction as well.

Perform the A* algorithm by hand to find the shortest path from the robot's starting location to the goal. Write down each step of the algorithm, including the current cell, open set of cells O, the closed set of cells C, the parent of each cell, and the current g-score and f-scores for each cell (these can be a sparse lists i.e. you don't need to write the scores/parents of the cells haven't been considered by the algorithm yet). You can use any heuristic you like, but specify the one you are using.

heuristic = manhattan distance (xa - xb) + (ya - yb) ..... and add it to distance from current node to neighbor node to find shortest path
**I'm only including the ones that follow the direction of the goal in my open set, i.e. to the right hand side or to the bottom, none to the left or up
and if it is the same row/column, it will stop considering diagonal paths

1) nc = 3,3
c = 3,3
o = {(3,2),(4,4),(3,4)} + the rest if you include the rest of the grid
g-score = 0
f-score = 11 .... |12-3| + |3-1|

if you take (4,2), f-score to ci = sqrt(2), f-score to cg= 9...9+1.4 = 10.4
if you take (3,2) and (3,4), ci f = 1, cg f = 10...10+1=11

2)nc = {4,2} 
p = {(3,3)}
c = {(3,3),(4,2)}
o = {(4,1),(5,1),(5,2)} + the rest if you include the rest of the grid
g-score = 1.4
f-score = 10  .... |12-4| + |1-2|

if you take (4,1),(5,2), ci f = 1, cg f = 8 ... 1+8=9
            (5,1), ci f = sqrt(2), cg f = 7... 1.4+7 = 8.4

3) nc = (5,1)
p = (4,2)
c = {(3,3), (4,2)}
o = (6,1) " "
g-score = 2.8
f-score = 7

4) nc = (6,1)
p = (5,1)
c = {(3,3), (4,2), (5,1)}
o = {(7,1)} " "
g-score = 3.8
f-score = 6

5) nc = (7,1)
p = (6,1)
c = {(3,3), (4,2), (5,1), (6,1)}
o = {(7,1)} " "
g-score = 4.8
f-score = 5

6) nc = (8,1)
p = (7,1)
c = {(3,3), (4,2), (5,1), (6,1),(7,1)}
o = {(8,1)} " "
g-score = 5.8
f-score = 4

7) nc = (9,1)
p = (8,1)
c = {(3,3), (4,2), (5,1), (6,1),(7,1), (8,1)}
o = {(9,1)} " "
g-score = 6.8
f-score = 3

8) nc = (10,1)
p = (9,1)
c = {(3,3), (4,2), (5,1), (6,1),(7,1), (8,1), (9,1)}
o = {(11,1)} " "
g-score = 7.8
f-score = 2

9) nc = (11,1)
p = (10,1)
c = {(3,3), (4,2), (5,1), (6,1),(7,1), (8,1), (9,1),(10,1)}
o = {(12,1)} " "
g-score = 8.8
f-score = 1

10) nc = (12,1)
p = (1,1)
c = {(3,3), (4,2), (5,1), (6,1),(7,1), (8,1), (9,1), (10,1), (11,1)}
o = {(12,1)} " "
g-score = 9.8
f-score = 0

## Question 3

List out the cells that represent the shortest path you found above. Then list the commands that would need to be sent to the robot to follow this path. The robot in question moves perfectly without any error, and reponds to two commands: it can either move forward a specified number of cells with `move(cells)`, or it can turn with `turn(radians)`. The robot should end at the goal the same direction at which it faced originally.
