# Marble Solitaire solution

  

## Problem overview

The board is represented as 7x7 matrix in code. Player would pick one marble will make it jump over one marble by moving the selected marble by two steps in left or right or up or down direction, and the marble which got jumped upon will be removed from the grid. The goal of the game is to have only one marble in this grid which should be at centre position i.e. (3,3) position.

  

## Code Details

1. Implemented the node class same as puzzle_eight problem.

2. Search agent search for only valid successors, this validity checker is implemented by function named is_valid move and then if the move is valid it is executed and added to successor list which is then searched in normal way.

3. After this we updated code with priority queue prioritizing nodes based on `f` value of a node which is sum of `g` and `h` values, where g is how far are we from initial state and h is heuristic function

    3.1. **Heuristic function:**  heuristic function is simple Manhattan distance calculator.

    3.2. **F-value:** we add g and h to get f and then prioritization of nodes is done on basis of this f value

  

## Difference in performance in both approaches

1. Number of nodes explored are less in heuristic approach. When we ran code this is the difference observed

    1.1. Number of nodes explored in *normal approach:* 963,871

    1.2. Number of nodes explored in *heuristic approach:* 846,818

2. This nodes were printed every 20 seconds and first approach gave output before `40` seconds but the heuristic approach took nearly `100` seconds so this heuristic approach takes computation time but less memory

  

## Output of both approaches

1. Normal approach

```plaintext

Nodes expanded: 510373

Nodes expanded: 963871

Solution Found

(1, 3, 3, 3)

(2, 1, 2, 3)

(0, 2, 2, 2)

(0, 4, 0, 2)

(4, 1, 2, 1)

(2, 4, 0, 4)

(2, 6, 2, 4)

(4, 6, 2, 6)

(4, 5, 2, 5)

(3, 4, 1, 4)

(0, 4, 2, 4)

(5, 4, 3, 4)

(3, 2, 1, 2)

(2, 0, 2, 2)

(4, 0, 2, 0)

(4, 3, 4, 1)

(6, 2, 4, 2)

(6, 4, 6, 2)

(3, 4, 1, 4)

(2, 6, 2, 4)

(1, 4, 3, 4)

(2, 3, 2, 1)

(0, 2, 2, 2)

(3, 4, 3, 2)

(3, 2, 1, 2)

(2, 0, 2, 2)

(1, 2, 3, 2)

(3, 2, 5, 2)

(6, 2, 4, 2)

(4, 1, 4, 3)

(5, 3, 3, 3)

```

1. Heuristic approach

```plaintext

Nodes expanded: 208608

Nodes expanded: 379855

Nodes expanded: 545033

Nodes expanded: 701182

Nodes expanded: 846818

Solution Found

(1, 3, 3, 3)

(2, 1, 2, 3)

(0, 2, 2, 2)

(0, 4, 0, 2)

(4, 1, 2, 1)

(2, 4, 0, 4)

(2, 6, 2, 4)

(4, 6, 2, 6)

(4, 5, 2, 5)

(3, 4, 1, 4)

(0, 4, 2, 4)

(5, 4, 3, 4)

(3, 2, 1, 2)

(2, 0, 2, 2)

(4, 0, 2, 0)

(4, 3, 4, 1)

(6, 2, 4, 2)

(6, 4, 6, 2)

(3, 4, 1, 4)

(2, 6, 2, 4)

(1, 4, 3, 4)

(2, 3, 2, 1)

(0, 2, 2, 2)

(3, 4, 3, 2)

(3, 2, 1, 2)

(2, 0, 2, 2)

(1, 2, 3, 2)

(3, 2, 5, 2)

(6, 2, 4, 2)

(4, 1, 4, 3)

(5, 3, 3, 3)

```
