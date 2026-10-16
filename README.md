# Data-Structure-Mini-Project-2

# Maze Generation Using DFS

A Python mini project that generates a maze using randomized Depth-First Search (DFS), also known as the recursive backtracking method. It uses an explicit stack, so it does not depend on Python's recursion limit.

## Features

- Prompts for the number of rows and columns (2 to 40)
- Generates a connected maze with one unique path between any two cells
- Marks an entrance at the top-left and an exit at the bottom-right
- Prints the maze as ASCII in the terminal
- Supports an optional seed to reproduce the same maze
- Uses only Python's standard library

## Requirements

- Python 3.10 or newer
- No third-party packages

## Run

From this folder, run:

```bash
python maze_dfs.py
```

Enter the number of rows and columns when prompted. Press Enter to use the default size of 10 rows by 20 columns.

For a repeatable maze, provide a random seed:

```bash
python maze_dfs.py --seed 7
```

## How the algorithm works

1. Start at the top-left cell and mark it visited.
2. Find its unvisited neighboring cells.
3. Choose one neighbor at random, remove the wall between the cells, mark the neighbor visited, and push it onto the stack.
4. If the current cell has no unvisited neighbors, pop the stack to backtrack.
5. Continue until the stack is empty.

Every cell is visited, and each newly visited cell is connected by removing exactly one wall. The result is a **perfect maze**: all cells are connected and there is exactly one path between any pair of cells.

## Data structures

- **2D grid:** stores the walls of every cell.
- **Stack:** stores the current DFS path and supports backtracking.
- **Visited matrix:** prevents the algorithm from revisiting cells.

## Complexity

For `R` rows and `C` columns, generation takes `O(R × C)` time and uses `O(R × C)` space.

## Project structure

```text
maze-generation-dfs/
├── README.md
└── maze_dfs.py
```

## Possible future improvements

- Display the maze as a graphical window
- Let users select entrance and exit positions
- Add a solver that finds and highlights the path through the generated maze
- Compare DFS generation with randomized Prim's or Kruskal's algorithms
