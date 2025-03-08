# Z3 Maze Solver

## Overview
This project demonstrates the use of **Satisfiability Modulo Theories (SMT)** with the **Z3 solver** to solve a maze problem. It formulates the maze navigation problem as a set of constraints and leverages Z3 to find a valid path from the entrance to the exit. Additionally, **PyQt5** is used to visualize both the maze and the computed solution path.

## Key Features
- **Z3 Solver Integration**: Uses constraint solving to determine a valid path through the maze.
- **Pathfinding Algorithm**: Ensures the solution adheres to movement constraints (no diagonal moves, must avoid walls).
- **Visualization with PyQt5**: Displays the maze, entrance, exit, walls, and the computed path interactively.
- **Flexible Maze Configuration**: The maze is defined as a 2D list, allowing easy modifications.

## How It Works (Algorithm Overview)
1. **Define the Maze**:
   - Represented as a 2D grid where `1` represents walls and `0` represents open paths.
   - The entrance and exit are explicitly set as walkable (`0`).

2. **Model the Problem with Z3**:
   - Boolean variables represent each cell (whether it is part of the solution path or not).
   - Constraints enforce:
     - The entrance and exit must be included in the path.
     - No walls (`1`) can be part of the path.
     - Each step in the path must be adjacent to the previous step (only up, down, left, or right; no diagonals).
   - An objective function ensures a valid, optimal path is found.

3. **Solve the Maze Using Z3**:
   - If a valid path is found, the solution is extracted and marked in the maze.
   - If no solution exists, the program notifies the user.

4. **Visualize the Solution with PyQt5**:
   - The maze is displayed graphically.
   - The path is drawn as a connected line between steps.
   - The entrance and exit are highlighted in different colors.

## Installation and Execution
### Requirements
Ensure you have the necessary dependencies installed:
```bash
pip install z3-solver PyQt5
```

### Running the Program
Run the script using Python:
```bash
python3 z3_maze.py
```

## File Structure
- `z3_maze.py` – Main script containing the maze definition, Z3 solving logic, and PyQt5 visualization.

## Notes
- The default maze is a `5x5` grid, but this can be modified within the script.
- The Z3 solver finds a feasible path, but optimization for shortest paths is not explicitly enforced.
- If no solution exists for the given maze configuration, the program will notify the user.

## License
This project is open-source and can be modified for educational and research purposes.

