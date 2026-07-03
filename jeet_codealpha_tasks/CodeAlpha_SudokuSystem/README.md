# Sudoku Solver (C++)

A console-based Sudoku solver that uses a **backtracking algorithm** to solve any valid 9x9 puzzle, with a colorful terminal UI to visualize the board.

## Features

- **Backtracking Solver** — recursively fills empty cells while respecting Sudoku rules
- **Colorful Terminal UI** — ANSI colors distinguish given clues, solved cells, and empty cells
- **Two Modes**
  - Solve a built-in sample puzzle
  - Enter your own puzzle interactively
- **Input Validation** — re-prompts if a row contains invalid digits
- **Performance Stats** — displays the number of backtracking steps and time taken to solve

## How It Works

| Component | Description |
|---|---|
| `isSafe()` | Checks whether a number can legally be placed in a cell (row, column, 3x3 box) |
| `solve()` | Recursive backtracking function that tries numbers 1–9 in each empty cell and backtracks on conflict |
| `printGrid()` | Renders the board with colors — yellow for given clues, green/cyan for solved cells |
| `getUserPuzzle()` | Reads a custom puzzle from the user, row by row, with validation |

## Getting Started

### Prerequisites

- A C++ compiler (e.g., `g++`)
- A terminal that supports ANSI escape codes (most Linux/macOS terminals; on Windows, use Windows Terminal or enable VT100 support)

### Compilation

```bash
g++ -o sudoku_solver main.cpp
```

### Run

```bash
./sudoku_solver
```

## Usage

On launch, choose between:

1. **Solve the built-in sample puzzle** — instantly solves a preloaded puzzle
2. **Enter my own puzzle** — type in 9 rows of 9 space-separated digits (use `0` for empty cells)

Example row input:
```
Row 1: 5 3 0 0 7 0 0 0 0
```

The solver then prints the unsolved grid, solves it, and displays the completed solution along with the number of steps and time taken.

## Project Structure

```
├── main.cpp      # Source code
└── README.md     # Project documentation
```

## Notes

- The built-in puzzle is a well-known example with a unique solution.
- If a puzzle has no valid solution, the program reports this instead of crashing.
- The algorithm has exponential worst-case time complexity, as with any brute-force backtracking approach, but solves typical 9x9 puzzles almost instantly.

## Possible Improvements

- [ ] Add puzzle validation before solving (detect contradictions in the initial grid)
- [ ] Load puzzles from a file
- [ ] Add a puzzle generator (not just a solver)
- [ ] Implement a more optimized solving strategy (e.g., constraint propagation / MRV heuristic) for harder puzzles
- [ ] Add step-by-step visualization of the solving process

## Author

Made as part of an internship project.

## License

This project is open source and available under the [MIT License](LICENSE).