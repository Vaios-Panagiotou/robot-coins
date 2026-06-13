# Robot Coins

This project explores different algorithmic approaches to solve the Robot Coins Problem: pure recursion, memoization, and dynamic programming (DP).

The task is to find the maximum number of coins a robot can collect while traversing an `n x m` grid from the top-left cell (1,1) to the bottom-right cell (n,m). The robot is restricted to moving only right or down. Cells contain either a coin (`C`) or are empty (`.`).

## Implementations

The repository provides three distinct solutions:

| Executable | Method | Path Output? | Description |
| :--- | :--- | :---: | :--- |
| `robotrec` | Recursive (Baseline) | No | A straightforward, recursive solution. |
| `robotmem` | Memoization | Yes | Recursive solution enhanced with an `n x m` memoization table. |
| `robotdp` | Iterative DP | Yes | An iterative DP solution, filling the table bottom-up. |

The `robotmem` and `robotdp` executables not only compute the maximum coin count but also reconstruct and print a corresponding optimal path.

## Build Instructions

The included `Makefile` allows for building all executables or a specific one.

```bash
# Build all executables
make

# Build specific executables
make robotrec
make robotmem
make robotdp

# Clean generated binaries and object files
make clean
```

## Running the Programs

All programs read the grid input from standard input (stdin).

**Input Format:**
- First Line: `n m` (grid dimensions: n rows, m columns).
- Next `n` Lines: `m` characters each (`C` for coin, `.` for empty).

**Example Execution:**

Assuming an input file like `data/grid7x8.txt`:

```bash
# Pure Recursive (Max coins only)
./robotrec < data/grid7x8.txt

# Memoized Recursion (Max coins + Path)
./robotmem < data/grid7x8.txt

# Iterative DP (Max coins + Path)
./robotdp < data/grid7x8.txt
```

**Output Structure:**

The final output will always state the maximum count:

```text
Maximum number of coins to pick up is : 13
```

For `robotmem` and `robotdp`, the path is printed first, detailing the coordinates and cumulative value:

```text
The path is :
.(1,1)/0 ---> C(2,1)/1 ---> ... ---> .(n,m)/K --->
Picked up K coins
```
